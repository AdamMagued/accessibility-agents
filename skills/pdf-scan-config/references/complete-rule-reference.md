# PDF Scan Config reference: Complete Rule Reference

Part of the `pdf-scan-config` skill. Read this only when the task reaches these sections.

## Complete Rule Reference

### Layer 1: PDF/UA Conformance Rules (PDFUA.*)

These map to ISO 14289-1 / Matterhorn Protocol 1.1 checkpoints. Rule IDs serve as stable identifiers across tooling, while the Matterhorn Checkpoint and Checkpoint Topic columns indicate the corresponding Matterhorn Protocol 1.1 checkpoint and topic. Disabling these means the scan will not catch PDF/UA conformance failures.

| ID | Matterhorn Checkpoint | Checkpoint Topic | Severity | What It Checks |
|----|-----------------------|------------------|----------|---------------|
| PDFUA.01.001 | 01 | Real Content | error | Structure tree root exists |
| PDFUA.01.002 | 01 | Real Content | error | MarkInfo/Marked flag is true |
| PDFUA.01.003 | 01 | Real Content | error | All content enclosed in structure elements |
| PDFUA.01.004 | 01 | Real Content | error | Structure elements have standard or role-mapped types |
| PDFUA.02.001 | 02 | Role Mapping | error | Role map targets are standard types |
| PDFUA.06.001 | 11 | Natural Language | error | Document-level language set |
| PDFUA.06.002 | 11 | Natural Language | error | Language identifier is valid BCP 47 |
| PDFUA.06.003 | 11 | Natural Language | warning | Language changes within text are tagged |
| PDFUA.07.001 | 14 | Headings | error | Heading levels don't skip |
| PDFUA.09.001 | 09 | Appropriate Tags | error | No off-page content tagged |
| PDFUA.11.001 | 11 | Natural Language | error | Text language determinable |
| PDFUA.13.001 | 13 | Graphics | error | Figure elements have /Alt text |
| PDFUA.13.002 | 13 | Graphics | warning | Alt text not excessively long |
| PDFUA.13.003 | 13 | Graphics | error | Decorative images marked as Artifact |
| PDFUA.14.001 | 13 | Graphics | error | Inline images tagged as Figure |
| PDFUA.15.001 | 17 | Mathematical Expressions | warning | Formulas tagged and have alt text |
| PDFUA.17.001 | 01 | Real Content | error | Artifacts not duplicated in structure tree |
| PDFUA.19.001 | 15 | Tables | error | Tables have TH cells |
| PDFUA.19.002 | 15 | Tables | error | TH cells have Scope |
| PDFUA.19.003 | 15 | Tables | error | Complex tables use Headers attribute |
| PDFUA.20.001 | 16 | Lists | error | Lists properly tagged |
| PDFUA.21.001 | 14 | Headings | error | Headings properly tagged |
| PDFUA.25.001 | 28 | Annotations | error | Tab order matches structure |
| PDFUA.26.001 | 24 | Non-Interactive Forms | error | Form fields have tooltips |
| PDFUA.26.002 | 24 | Non-Interactive Forms | error | Form fields in structure tree |
| PDFUA.26.003 | 24 | Non-Interactive Forms | warning | Form field tab order is ordered |
| PDFUA.28.001 | 28 | Annotations | error | Link annotations in structure tree |
| PDFUA.28.002 | 28 | Annotations | error | Links have descriptions |
| PDFUA.30.001 | 06 | Metadata | error | XMP and Info dict consistent |
| PDFUA.31.001 | 06 | Metadata | error | PDF/UA identification present |

### Layer 2: Best-Practice Rules (PDFBP.*)

Each row, with ID, severity and what it checks.

| ID | Severity | What It Checks |
|----|----------|---------------|
| PDFBP.META.TITLE_PRESENT | error | Title metadata exists |
| PDFBP.META.TITLE_DISPLAY | warning | Title bar shows document title |
| PDFBP.META.LANG_PRESENT | error | Language metadata exists |
| PDFBP.META.TAGGED_MARKER | error | Tagged PDF marker present |
| PDFBP.TEXT.EXTRACTABLE | error | Text can be programmatically read |
| PDFBP.TEXT.UNICODE_MAP | warning | Fonts have ToUnicode maps |
| PDFBP.TEXT.EMBEDDED_FONTS | warning | Fonts are embedded |
| PDFBP.TEXT.ACTUAL_TEXT | warning | Special glyphs have ActualText |
| PDFBP.STRUCT.STRUCTURE_TREE_PRESENT | error | Structure tree exists |
| PDFBP.STRUCT.READING_ORDER | warning | Reading order matches visual order |
| PDFBP.IMG.ALT_PRESENT | error | All figures have alt text |
| PDFBP.IMG.ALT_QUALITY | warning | Alt text is meaningful |
| PDFBP.IMG.DECORATIVE_ARTIFACT | tip | Decorative images are artifacts |
| PDFBP.NAV.BOOKMARKS_FOR_LONG_DOCS | warning | Long docs have bookmarks |
| PDFBP.NAV.TOC_LINKED | tip | TOC entries are linked |
| PDFBP.TAB.TH_PRESENT | error | Tables have headers |
| PDFBP.TAB.SCOPE_SET | warning | Headers have scope |
| PDFBP.TAB.COMPLEX_HEADERS | warning | Complex tables use Headers attr |
| PDFBP.FORMS.TAB_ORDER | warning | Form tab order follows structure |
| PDFBP.FORMS.TOOLTIP_PRESENT | error | Form fields have labels |
| PDFBP.LINK.IN_STRUCT | error | Links in structure tree |
| PDFBP.LINK.DESCRIPTIVE_TEXT | warning | Link text is descriptive |

### Layer 3: Quality/Pipeline Rules (PDFQ.*)

Each row, with ID, severity and what it checks.

| ID | Severity | What It Checks |
|----|----------|---------------|
| PDFQ.REPO.NO_SCANNED_ONLY | error | No image-only PDFs in repo |
| PDFQ.REPO.ENCRYPTED | warning | PDF not encrypted |
| PDFQ.PIPE.SOURCE_REBUILD | tip | Suggest source rebuild |
| PDFQ.PIPE.VERAPDF_VALIDATE | tip | Suggest veraPDF validation |
