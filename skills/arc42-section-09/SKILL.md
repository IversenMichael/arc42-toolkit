---
name: arc42-section-09
version: 2.0.0
description:
  Interactively guides the documentation of arc42 Section 9 (Architecture
  Decisions) in the form of the official arc42 template. Asks which decisions
  are architecturally significant, their context, alternatives and consequences,
  and lets the user choose between ADRs, a table or one subsection per decision,
  then iterates until the user is satisfied.
---

# arc42 Section 9: Architecture Decisions

You help document Section 9 of an arc42 architecture documentation. Follow the
official template at <https://docs.arc42.org/section-9/>.

Section 9 records important, expensive, large-scale or risky architecture
decisions together with their rationale. A decision means selecting one
alternative based on given criteria. Stakeholders should be able to comprehend
and retrace the decisions. Avoid redundancy: Section 4 already captures the most
important decisions, so refer to it. A decision that only concerns one building
block may be documented locally in its white box in Section 5.

arc42 offers three forms:

- an architecture decision record (ADR) for every important decision
- a list or table, ordered by importance and consequences
- a separate subsection per decision, for more detail

## Step 1: Ask Before Writing

Do not draft anything until the questions below are answered.

First read Section 4 (decisions summarized there are only referenced here),
Section 2 (constraints that forced decisions) and Section 1.2 (quality goals the
decisions serve) if they exist.

1. Which decisions are architecturally significant? Those that affect the
   structure, the quality characteristics, important dependencies or interfaces,
   or construction techniques. Implementation details do not belong here.
2. Which form does the user want: ADRs, a table, or subsections?
3. Per decision:
   - Title: a proper name, for example "Strategy pattern for multiple checking
     algorithms".
   - Context: the situation, including technical, political, social and project
     forces, which may be in tension.
   - Decision criteria: what mattered when choosing.
   - Decision: the chosen alternative, as a reply to the forces.
   - Rejected alternatives and why they were rejected.
   - Status: proposed, accepted, deprecated or superseded, with a reference to
     the replacement.
   - Consequences: all of them, positive, negative and neutral.
   - Timestamp: when it was decided, and by whom.

## Step 2: Draft the Section

Produce the section in the chosen form. The ADR form below follows the Nygard
structure that arc42 recommends. Order the table form by importance and
consequences.

```markdown
# 9. Architecture Decisions

## 9.1 ADR 1: [Title]

Status: [proposed | accepted | deprecated | superseded by ADR n]

Date: [YYYY-MM-DD]

Context: [The forces at play: technical, political, social, project.]

Decision: [What was decided, in response to the forces.]

Consequences: [What becomes easier or harder as a result. Positive, negative and
neutral consequences.]

Alternatives: [Rejected options and the reasons for rejecting them.]

## 9.2 ADR 2: [Title]

[Same structure.]
```

Table form:

```markdown
# 9. Architecture Decisions

| Decision   | Rationale           | Consequences            | Status   | Date         |
| ---------- | ------------------- | ----------------------- | -------- | ------------ |
| [Decision] | [Why, and criteria] | [Positive and negative] | [Status] | [YYYY-MM-DD] |
```

## Step 3: Review and Iterate

Check the draft against the arc42 guidance. For every failed item, explain what
is wrong and how to fix it.

- Is every entry architecturally relevant?
- Does every decision state its reasons and the criteria that were applied?
- Are rejected alternatives recorded for important decisions?
- Are all consequences listed, not only the positive ones?
- Does every decision carry a status and a timestamp?
- Is the section free of redundancy with Section 4? Decisions summarized there
  are referenced, not repeated.
- Could any decision be documented locally in Section 5 instead?

Cross-section consistency, where the sections exist:

- Decisions do not violate the constraints of Section 2.
- Building block names match Section 5.
- Risks that follow from decisions appear in Section 11.

Then ask what the user wants to refine and iterate until they are satisfied.

Based on <https://docs.arc42.org/section-9/>, the arc42 template by Dr. Gernot
Starke and Dr. Peter Hruschka (CC BY-SA 4.0), and Michael Nygard, Documenting
Architecture Decisions (2011).
