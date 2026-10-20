---
name: arc42-section-01
version: 2.0.0
description:
  Interactively guides the documentation of arc42 Section 1 (Introduction and
  Goals) in the form of the official arc42 template. Asks about requirements,
  quality goals and stakeholders before drafting, then iterates until the user
  is satisfied.
---

# arc42 Section 1: Introduction and Goals

You help document Section 1 of an arc42 architecture documentation. Follow the
official template at <https://docs.arc42.org/section-1/>.

Section 1 describes the requirements and driving forces that the architects and
the development team must consider:

- underlying business goals, essential features and essential functional
  requirements
- quality goals for the architecture
- relevant stakeholders and their expectations

arc42 splits the section into 1.1 Requirements Overview, 1.2 Quality Goals and
1.3 Stakeholders. All parts of arc42 are optional; use what the stakeholders
need.

## Step 1: Ask Before Writing

Do not draft anything until the questions below are answered. Ask follow-up
questions when an answer is vague, in particular for quality goals.

First check which other sections already exist, in particular Section 10
(Quality Requirements) and Section 3 (Context and Scope), and read them.

1. System and business goals. What is the system called? Which business activity
   does it support or improve, and why is it being created or changed?
2. Essential features and functional requirements. Which tasks and use cases are
   essential? Group related requirements when there are many. Does a
   requirements document, backlog or specification exist? If so, record its
   name, version and where to find it.
3. Quality goals for the architecture. Which three, and at most five, quality
   goals matter most to the major stakeholders? Ask for architecture quality
   goals, not project goals such as deadlines or budget. For each goal ask for a
   concrete scenario that shows what the goal means, and for its priority. Offer
   the ISO 25010:2023 categories or the arc42 quality model
   (<https://quality.arc42.org>) as a checklist if the user struggles. If no
   stakeholder can state quality goals, agree on explicit assumptions and mark
   them as assumptions.
4. Stakeholders. Which persons, roles or organizations should know the
   architecture, have to be convinced of it, work with it or with the code, need
   its documentation, or decide about the system? For each: a contact and what
   they expect from the architecture and its documentation. Search broadly:
   operations, support, testers, auditors and neighbouring teams are often
   forgotten. If management already maintains a stakeholder table, link to it
   instead of duplicating it.

## Step 2: Draft the Section

Produce the section in the arc42 form below. Keep 1.1 as short as possible and
refer to existing requirements documents instead of copying them.

```markdown
# 1. Introduction and Goals

## 1.1 Requirements Overview

[Short description of the business goals, the driving forces and the essential
functional requirements. Prose, a bullet list or a tabular use-case overview.]

| Use Case | Description |
| -------- | ----------- |
| [Name]   | [One line]  |

Requirements documents: [name, version and location of each document]

## 1.2 Quality Goals

[Three to five quality goals for the architecture, ordered by priority, each
with a concrete scenario.]

| Priority | Quality Goal | Scenario                                 |
| -------- | ------------ | ---------------------------------------- |
| 1        | [Goal]       | [Concrete situation that shows the goal] |
| 2        | [Goal]       | [Concrete situation that shows the goal] |
| 3        | [Goal]       | [Concrete situation that shows the goal] |

The complete quality requirements are in Section 10.

## 1.3 Stakeholders

| Role/Name | Contact   | Expectations                                      |
| --------- | --------- | ------------------------------------------------- |
| [Role]    | [Contact] | [What they expect from the architecture and docs] |
```

## Step 3: Review and Iterate

Check the draft against the arc42 guidance. For every failed item, explain what
is wrong and how to fix it.

Requirements overview:

- Is it a compact summary rather than a copy of the requirements? It should
  balance readability against redundancy with existing documents.
- Are business goals and the essential use cases visible?
- Are existing requirements documents referenced with version and location?

Quality goals:

- Are there at most five goals, ordered by priority?
- Are they quality goals for the architecture, not project goals?
- Is every goal concrete, free of buzzwords, and illustrated by a scenario?
- Are assumptions marked as such when no stakeholder provided the goals?
- Are the detailed and complete quality requirements deferred to Section 10
  rather than listed here?

Stakeholders:

- Does the table name roles, persons and their expectations towards the
  architecture and its documentation, rather than repeating their functional or
  quality requirements?
- Are obvious roles missing, such as operations for a deployed system?

Cross-section consistency, where the sections exist:

- Section 4 should state a solution approach for every quality goal in 1.2.
- Section 10 should reference the goals in 1.2 instead of restating them.

Then ask what the user wants to refine and iterate until they are satisfied.

Based on <https://docs.arc42.org/section-1/> and the arc42 template by Dr. Gernot
Starke and Dr. Peter Hruschka (CC BY-SA 4.0).
