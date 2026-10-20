---
name: arc42-review
version: 2.0.0
description:
  Reviews any arc42 section or the full document against the content, motivation
  and form that the official arc42 template prescribes for each section, and
  against the consistency between sections. Produces a findings report with
  severity and fixes, and offers to resolve critical findings with the relevant
  section skill.
---

# arc42 Review

You review arc42 architecture documentation against the official arc42 template
(<https://docs.arc42.org>). arc42 prescribes the content and the form of each
section but no notation, no identifier scheme and no fixed depth; all sections
are optional. Review what the stakeholders need, not what a checklist could
demand.

## Step 1: Identify What to Review

Ask the user, unless already clear:

1. Which files hold the documentation, and which sections should be reviewed:
   one section, a related set, or the full document?
2. Who are the stakeholders of the documentation, if Section 1.3 does not say?

Read the files directly. Do not ask the user to paste content.

## Step 2: Review

Apply the universal checks to every section, then the section-specific checks,
then the cross-section checks.

### Universal Checks

- The section has the arc42 number and name.
- The content matches what arc42 describes for the section, and nothing that
  belongs in another section is placed here.
- The form matches what arc42 suggests for the section, or a stated reason
  explains the deviation.
- The section is as short as it can be; text that repeats another section is
  replaced by a reference.
- Terms are used as defined in Section 12.

### Section-Specific Checks

| Section | Checks                                                                                                                                                                                                                                          |
| ------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 1       | 1.1 is a short overview that references requirements documents; 1.2 has at most five concrete, prioritized architecture quality goals with scenarios; 1.3 lists stakeholders with their expectations towards the architecture and documentation |
| 2       | Constraints are imposed from outside, have an explanation and consequences, and are not decisions or quality goals                                                                                                                              |
| 3       | The system is one black box; all communication partners with inputs and outputs are shown in a diagram and a table; the technical context, if present, maps inputs and outputs to channels                                                      |
| 4       | Short; covers technology, decomposition, quality goal approaches and organization; every decision is motivated; details are referenced in Sections 5, 8 and 9                                                                                   |
| 5       | Level 1 white box has a diagram, a motivation and black boxes with responsibilities; external interfaces match Section 3; source code is locatable; only relevant blocks are refined, each refinement justified                                 |
| 6       | A few representative, architecturally relevant scenarios; every activity maps to a building block of Section 5; notable aspects are explained                                                                                                   |
| 7       | All relevant environments; level 1 has a diagram, a motivation, quality features and the mapping of all building blocks; level 2 only where needed                                                                                              |
| 8       | Only needed concepts, one subsection each, each explaining how it works and which building blocks it concerns; domain model present or consciously omitted                                                                                      |
| 9       | Only significant decisions; each has context, decision, status, consequences, rationale and timestamp; no redundancy with Section 4                                                                                                             |
| 10      | 1.2 referenced, not repeated; overview by category; scenarios specific and measurable; usage and change scenarios considered                                                                                                                    |
| 11      | Prioritized list of risks and debts with descriptions and suggested measures; sources searched: stakeholders, interfaces, evaluation, processes, data, code                                                                                     |
| 12      | One compact table of terms and definitions; synonyms and homonyms resolved; terms used consistently elsewhere                                                                                                                                   |

### Cross-Section Checks

| Relationship     | Check                                                                                   |
| ---------------- | --------------------------------------------------------------------------------------- |
| 1.2 and 4        | Every quality goal has a solution approach in Section 4                                 |
| 1.2 and 10       | Section 10 references the goals of 1.2 and adds the remaining quality requirements      |
| 2 and 4, 5, 7, 9 | No decision, structure or deployment violates a constraint                              |
| 3 and 5          | The external interfaces at level 1 are the communication partners of Section 3          |
| 3.2 and 7        | Section 7 refines the infrastructure black box of 3.2                                   |
| 4 and 5          | The decomposition in Section 4 is the level 1 structure of Section 5                    |
| 4 and 9          | Section 9 details, and does not repeat, the decisions summarized in Section 4           |
| 5 and 6, 7, 8    | Sections 6, 7 and 8 use the building block names of Section 5, and 7 maps all of them   |
| 8 and 12         | The domain model and the glossary agree                                                 |
| 9, 10 and 11     | Open negative consequences and unmet quality requirements appear as risks in Section 11 |

## Step 3: Report Findings

```markdown
## Review Report: [Section N | Sections N and M | Full Document]

### Summary

[Two or three sentences: overall state and the most important finding.]

### Findings

| Severity | Section | Finding   | Fix                               |
| -------- | ------- | --------- | --------------------------------- |
| Critical | [N]     | [Problem] | [What to change, and which skill] |
| Major    | [N]     | [Problem] | [Fix]                             |
| Minor    | [N]     | [Problem] | [Fix]                             |

Critical: the section does not fulfil its arc42 purpose. Major: stakeholders
will miss or misunderstand something. Minor: form and wording.

### Cross-Section Consistency

| Relationship | Status      | Detail      |
| ------------ | ----------- | ----------- |
| [Pair]       | PASS / FAIL | [If failed] |

### Verdict

[Ready | Needs work | Not ready], with the reason in one sentence.
```

## Step 4: Offer to Fix

For every critical finding, offer to resolve it now with the relevant
arc42-section-NN skill. Do not change files without the user's agreement.

Based on <https://docs.arc42.org> and the arc42 template by Dr. Gernot Starke and
Dr. Peter Hruschka (CC BY-SA 4.0).
