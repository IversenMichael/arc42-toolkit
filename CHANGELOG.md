# Changelog

All notable changes to the arc42-toolkit skills are documented here.

The format follows [Keep a Changelog](https://keepachangelog.com/en/1.0.0/).
Each skill uses [Semantic Versioning](https://semver.org/spec/v2.0.0.html):
`MAJOR.MINOR.PATCH`.

- **MAJOR** — breaking change to the skill interface or output structure
- **MINOR** — new capability added in a backwards-compatible way
- **PATCH** — bug fix or wording improvement that does not change behavior

---

## [2.0.0] — Unreleased

### Changed

All skills now follow the content, motivation and form of the official arc42
template (https://docs.arc42.org) and nothing else. Toolkit conventions that had
no basis in arc42, or that contradicted it, were removed. All skills are bumped
to `2.0.0` because the output structure changes.

| Artifact           | Change                                                                                                                                                                                                                                                                   |
| ------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| All section skills | Depth levels (LEAN / ESSENTIAL / THOROUGH), mandated C4 PlantUML files, "Overview" paragraphs and identifier schemes (IF-xx, QS-xx, RISK-xx, DEBT-xx, ADR-xxx) removed; questions and checklists derived from the arc42 Content, Form and Practical Tips of each section |
| `arc42-section-01` | Sign-off field, Q42 tags and mandatory 3-5 goals removed; at most five prioritized goals with scenarios; 1.1 as short overview with references; 1.3 renamed to Stakeholders with expectations towards the architecture and its documentation                             |
| `arc42-section-02` | Renamed to Architecture Constraints; "non-negotiable" rule replaced by arc42's "must be dealt with, may be negotiable"; the three arc42 categories (technical, organizational and political, conventions)                                                                |
| `arc42-section-03` | Business context as black box diagram plus partner / inputs / outputs table; technical context with mapping of inputs and outputs to channels; may be deferred to Section 7                                                                                              |
| `arc42-section-04` | The four arc42 content areas and the arc42 table (quality goal, scenario, solution approach, link to details); organizational decisions instead of Conway's law analysis                                                                                                 |
| `arc42-section-05` | arc42 white box and black box templates; 5.1 Whitebox Overall System, 5.2 Level 2, 5.3 Level 3; building blocks may be any granularity arc42 lists; circular dependency and "no classes" rules removed                                                                   |
| `arc42-section-06` | Four arc42 scenario areas, representative selection instead of 3-5 with a mandatory mix; arc42 notations; per-scenario structure of diagram or steps plus notable aspects                                                                                                |
| `arc42-section-07` | 7.1 Infrastructure Level 1 (diagram, motivation, quality features, mapping) repeated per environment, 7.2 Infrastructure Level 2; network and TLS checklist removed                                                                                                      |
| `arc42-section-08` | Fixed 8.1-8.7 topics replaced by the arc42 topic collection as a checklist and one subsection per chosen concept                                                                                                                                                         |
| `arc42-section-09` | The three arc42 forms (ADR, table, subsections); Nygard ADR fields plus timestamp and rejected alternatives; decision log, implications block and validation removed                                                                                                     |
| `arc42-section-10` | 10.1 overview by category, 10.2 scenarios in arc42 short or long form; usage and change scenarios; 10.3 aspirational scenarios removed                                                                                                                                   |
| `arc42-section-11` | Prioritized list or table with suggested measures; questions follow the six arc42 search tips; probability-impact matrix and per-risk sections removed                                                                                                                   |
| `arc42-section-12` | One term / definition table with optional translation columns; sub-tables removed                                                                                                                                                                                        |
| `arc42-review`     | Checks derived from the arc42 content and form of each section and from the name-based relations between sections                                                                                                                                                        |
| `arc42-lint`       | Name-based consistency rules; notes that `scripts/arc42-lint.py` checks the removed identifier conventions                                                                                                                                                               |
| `AGENTS.md`        | Toolkit conventions replaced by the arc42 principles and the name-based cross-section relations                                                                                                                                                                          |

---

## [1.1.1] — 2026-07-07

### Fixed

Clarified the boundary between official arc42 guidance and toolkit conventions
throughout all skills and documentation. No changes to executable code or
scripts. Skill prompt wording changes may affect generated output structure
(e.g., Section 10 overview format is now flexible rather than a forced quality
tree; Section 9 alternatives table is now conditional on real alternatives
existing).

| Artifact                     | Change                                                                                                                                                                                                                                     |
| ---------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `README.md`                  | Badge changed from `arc42-compliant` to `arc42-based`; Section 1.2 reframed as toolkit recommendation; depth levels labelled as toolkit conventions; C4 PlantUML noted as toolkit default                                                  |
| `AGENTS.md`                  | Aligned with README framing: depth levels, C4 PlantUML, and Section 1.2 recommendation all labelled as toolkit conventions                                                                                                                 |
| `arc42-lint` → `1.0.1`       | Renamed to "arc42 Toolkit Convention Linter"; all five rules reworded from "must" to "should/toolkit convention"; findings say "toolkit convention deviation" not "error"                                                                  |
| `arc42-review` → `1.0.1`     | Legend added to section-specific checks; all toolkit-specific items tagged `(toolkit)`; Nygard base fields now complete (Title, Context, Decision, Status, Consequences); quality overview source corrected to `docs.arc42.org/section-10` |
| `arc42-section-01` → `1.0.1` | Section `1.3` heading corrected to singular "Stakeholder" per official arc42 template                                                                                                                                                      |
| `arc42-section-05` → `1.0.1` | Section `5.1` heading changed to "Whitebox Overall System" per official arc42 template name                                                                                                                                                |
| `arc42-section-09` → `1.0.1` | ADR format credited to Nygard; alternatives table and implications block labelled as toolkit additions; alternatives table now conditional on real alternatives existing; Date field labelled as toolkit addition                          |
| `arc42-section-10` → `1.0.1` | Quality Requirements Overview replaces forced quality tree; Q42 coaching references `quality.arc42.org`; QS-xx IDs and Section 10.3 labelled as toolkit conventions                                                                        |
| `arc42-section-11` → `1.0.1` | RISK-xx and DEBT-xx ID conventions labelled at the top of the skill                                                                                                                                                                        |

---

## [1.1.0] — 2026-05-16

### Added

| Artifact                   | Description                                                                                                                                                                                                                                                                               |
| -------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `scripts/arc42-lint.py`    | Standalone Python linter (stdlib only) — validates cross-section ID consistency across 5 rules: IF-xx Section 3↔Section 5, building block names Section 5↔Section 7, Q42 tags Section 1↔Section 10, RISK-xx references Section 9↔Section 11, aspirational scenarios Section 10↔Section 11 |
| `scripts/languages/`       | Language definition files (en, de, fr, it, es, pt) — section keywords and content patterns per language; contributors can add new files                                                                                                                                                   |
| `templates/arc42-lint.yml` | GitHub Actions workflow template — copy to `.github/workflows/` in your project to run the linter automatically on `docs/**` changes                                                                                                                                                      |
| `skills/arc42-lint/`       | New skill — AI-assisted consistency linting via `/arc42-lint`; runs the script when available, applies rules manually when not, and offers to fix any issues found                                                                                                                        |

---

## [1.0.0] — 2026-05-16

Initial versioned release. All skills ship at `1.0.0`, aligned with the
`arc42-toolkit` plugin version in `.claude-plugin/plugin.json`.

### Added

| Skill              | Description                                                    |
| ------------------ | -------------------------------------------------------------- |
| `arc42-section-01` | Interactive guide for Section 1 — Introduction and Goals       |
| `arc42-section-02` | Interactive guide for Section 2 — Constraints                  |
| `arc42-section-03` | Interactive guide for Section 3 — Context and Scope            |
| `arc42-section-04` | Interactive guide for Section 4 — Solution Strategy            |
| `arc42-section-05` | Interactive guide for Section 5 — Building Block View          |
| `arc42-section-06` | Interactive guide for Section 6 — Runtime View                 |
| `arc42-section-07` | Interactive guide for Section 7 — Deployment View              |
| `arc42-section-08` | Interactive guide for Section 8 — Crosscutting Concepts        |
| `arc42-section-09` | Interactive guide for Section 9 — Architecture Decisions (ADR) |
| `arc42-section-10` | Interactive guide for Section 10 — Quality Requirements        |
| `arc42-section-11` | Interactive guide for Section 11 — Risks and Technical Debt    |
| `arc42-section-12` | Interactive guide for Section 12 — Glossary                    |
| `arc42-review`     | Cross-section quality review with severity-linked fixes        |
