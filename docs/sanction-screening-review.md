# Sanction Screening Tool — Review & Working Notes

> Carry-over context for continuing work in a new Claude Code session.
> Created 2026-06-19. Owner: d.erts@unlimit.com.

## Source

- **Notebook:** `SanctionScreening_2` (Google Colab)
- **Drive file ID:** `1iAhtO9D0mGqMka_Zmt2-g5yS5f1p2Zl4`
- **URL:** https://colab.research.google.com/drive/1iAhtO9D0mGqMka_Zmt2-g5yS5f1p2Zl4
- Reachable via the Google Drive connector when authenticated as the owner
  account. Re-fetch with `download_file_content` (content is base64-encoded
  `.ipynb` JSON), then decode + extract cells.

## What the tool is

A **sanctions name-screening fuzzy matcher** (not a document parser). Pipeline:

1. **Normalize** each name: lowercase → spell out numbers (`inflect`) → strip
   legal suffixes (LTD/LLC/OOO/…) via a regex stop-word list → strip
   punctuation → collapse whitespace.
2. **Cross-compare** every input/client name against every sanction-list name
   using four signals:
   - Jaccard (token overlap)
   - Dice (character-bigram overlap)
   - Jaro-Winkler (typo distance)
   - Metaphone (phonetic equality, binary)
3. **Score:** `final = 0.40·max(jaccard,dice) + 0.40·jaro + 0.20·phonetic`,
   flag if `>= 0.60`, bucket into Low (≥0.60) / Medium (≥0.75) / High (≥0.85).

The notebook has 12 code cells with heavy duplication: cells 0/6/8 redefine the
same config, 2/9/11 redefine the same functions, and 3/5/10 are three
near-identical "run" variants (Drive-write / Drive-local / manual-upload).

## Review findings (priority order)

### 🔴 Compliance-critical
1. **Over-aggressive normalization silently drops entities.** Stop-word list
   strips real name tokens (`PUBLIC`, `GROUP`, `HOLDINGS`, `FOUNDATION`,
   `GLOBAL`, `WORLDWIDE`, `INTERNATIONAL`, plus 2-letter `CO/SA/AG/AS/AO/AB/NV/BV`).
   A name like "Holdings Group International" normalizes to `""`, and
   `preprocess_dataframe` **drops empty-normalized rows** → that party is
   **never screened**. Worst-case failure for a screening tool.
   - Fix: split "legal-form suffixes to strip" from a small, deliberate stop set;
     never drop a record — keep the original name as a fallback comparison.
2. **No alias / AKA / weak-alias matching.** Only the primary name column is
   compared. OFAC SDN / EU / UN / UK lists carry many aliases & transliterations
   per entity; DOB / entity-type / country are ignored (those normally *reduce*
   false positives).
3. **No transliteration / diacritic folding.** Cyrillic-derived forms present
   (OOO/OAO/PAO) but no transliteration and no NFKD accent folding (`é`≠`e`).
4. **Phonetic over whole multi-word string + binary 0/1 × 0.20 weight** is
   coarse: can push unrelated names over threshold (false positives) or
   contribute nothing for multi-token near-matches. Should be per-token.
5. **No exact-match fast path.** A perfectly matching normalized name should be
   a definitive hit independent of fuzzy weighting.

### 🟠 Correctness / robustness
6. **Fragile column handling.** `header=None, skiprows=1` + forcing first two
   columns to `['Name','ID']` assumes name-then-ID order & exactly one header
   row; differently-ordered CSVs mismatch silently. Detect by header name.
7. **Number-to-words mangles data** if names contain years/codes.
8. **Stale-cache risk.** `if 'sanction_df' not in globals()` caches the list in
   memory; swapping the DB file keeps the old one until runtime restart. Cache
   keyed on file mod-date would be safer for frequently-updated lists.

### 🟡 Performance / maintainability
9. **O(n×m) `iterrows` nested loop in pure Python.** OFAC SDN alone ~17k names
   × client book = millions–billions of comparisons → unusably slow.
   - Fix: use **`rapidfuzz`** (C-backed) + **blocking/indexing** (group
     candidates by phonetic key or first token) to avoid all-vs-all.
10. **De-duplicate the notebook** to one config + one function module + one
    parametrized run.
11. **No audit trail / list-version stamp / false-positive (whitelist)
    suppression** — all expected for an auditable screening tool.

## Open questions (blockers before changing matching logic)
- Which jurisdictions/lists? (OFAC, EU, UN, UK OFSI, local?)
- Entities only, or also individuals / PEPs? (drives alias/DOB/transliteration)
- Is the goal to improve THIS matcher, or also build the document-parsing side
  (the originally-mentioned "corporate & KYC document parsing")? These are two
  distinct tools.

## Proposed next steps
- [ ] Get answers to the open questions above.
- [ ] Refactor to a single clean flow: de-duplicated, `rapidfuzz` + blocking,
      safe normalization (never drops records), alias-aware, exact-match path,
      list-date stamping, basic audit log.
- [ ] Decide deliverable form: cleaned `.ipynb`/`.py` handed back, vs.
      version-controlled module committed to this branch.

---
*Branch: `claude/kyc-screenet-doc-parsing-evma3f`.*
