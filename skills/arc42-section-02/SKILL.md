---
name: arc42-section-02
version: 2.0.0
description:
  Interactively guides the documentation of arc42 Section 2 (Architecture
  Constraints) in the form of the official arc42 template. Asks about technical,
  organizational and political constraints and conventions before drafting, then
  iterates until the user is satisfied.
---

# arc42 Section 2: Architecture Constraints

You help document Section 2 of an arc42 architecture documentation. Follow the
official template at <https://docs.arc42.org/section-2/>.

Section 2 lists every requirement that constrains the architects in their
freedom of design and implementation decisions, or in decisions about the
development process. Constraints often go beyond the single system and hold for
whole organizations. Architects should know exactly where they are free and
where they must adhere to constraints. Constraints must always be dealt with,
but they may be negotiable.

## Step 1: Ask Before Writing

Do not draft anything until the questions below are answered.

First check whether Sections 4 (Solution Strategy) and 9 (Architecture
Decisions) exist. A constraint is given to the architects from outside; a choice
the architects made themselves is a decision and belongs in Section 4 or 9.

1. Technical constraints. Mandated hardware, software, operating environments,
   programming languages, frameworks, middleware, protocols, or existing systems
   that must be used or integrated.
2. Organizational and political constraints. Organization and structure of the
   team, resources, budget, schedule, mandated development process, procurement
   rules, legal and regulatory obligations, and decisions by management or the
   parent organization.
3. Conventions. Programming, versioning, documentation and naming guidelines,
   architecture or coding standards that must be followed.
4. For each constraint: What is its background? What are its consequences for
   the architecture? Is it negotiable, and with whom? Do constraints of other
   systems in the organization also apply to this one?

## Step 2: Draft the Section

Produce the section in the arc42 form: simple tables of constraints with
explanations. Subdivide into the three categories only when it helps; a single
table is fine for a few constraints. Omit empty categories.

```markdown
# 2. Architecture Constraints

## 2.1 Technical Constraints

| Constraint   | Explanation                                          |
| ------------ | ---------------------------------------------------- |
| [Constraint] | [Background, consequences, whether it is negotiable] |

## 2.2 Organizational and Political Constraints

| Constraint   | Explanation   |
| ------------ | ------------- |
| [Constraint] | [Explanation] |

## 2.3 Conventions

| Convention   | Explanation   |
| ------------ | ------------- |
| [Convention] | [Explanation] |
```

## Step 3: Review and Iterate

Check the draft against the arc42 guidance. For every failed item, explain what
is wrong and how to fix it.

- Does every constraint have an explanation of its background and its
  consequences for the architecture?
- Is every entry really a constraint imposed from outside? Entries the
  architects chose themselves belong in Section 4 or Section 9.
- Is every entry a constraint rather than a quality goal? Statements such as
  "must be secure" belong in Section 1.2 or Section 10.
- Are organizational constraints and conventions covered, not only technical
  ones?
- Is it stated which constraints are negotiable?

Cross-section consistency, where the sections exist:

- Section 4 and Section 9 must not contradict the constraints listed here.
- Sections 5 and 7 must be compatible with the technical constraints.

Then ask what the user wants to refine and iterate until they are satisfied.

Based on <https://docs.arc42.org/section-2/> and the arc42 template by Dr. Gernot
Starke and Dr. Peter Hruschka (CC BY-SA 4.0).
