---
name: arc42-section-10
version: 2.0.0
description:
  Interactively guides the documentation of arc42 Section 10 (Quality
  Requirements) in the form of the official arc42 template. Asks for an overview
  of quality requirements by category and for specific, measurable usage and
  change scenarios before drafting 10.1 and 10.2, then iterates until the user
  is satisfied.
---

# arc42 Section 10: Quality Requirements

You help document Section 10 of an arc42 architecture documentation. Follow the
official template at <https://docs.arc42.org/section-10/>.

Section 10 contains all relevant quality requirements. The most important ones
are already in Section 1.2 as quality goals and are only referenced here. This
section additionally captures quality requirements of lesser importance, which
create no high risk when not fully achieved. Quality requirements strongly
influence architecture decisions, so they must be specific and measurable.

The section has two parts:

- 10.1 Quality Requirements Overview: a summary by category or topic.
- 10.2 Quality Scenarios: concrete scenarios that act as acceptance criteria. If
  the overview is already precise and measurable, 10.2 may be skipped.

## Step 1: Ask Before Writing

Do not draft anything until the questions below are answered.

First read Section 1.2 if it exists and list its quality goals to the user.

1. Overview. Beyond the goals in 1.2, which quality requirements exist? Use the
   categories of ISO 25010:2023 or the arc42 quality model
   (<https://quality.arc42.org>) as a checklist: functional suitability,
   performance efficiency, compatibility, interaction capability (usability),
   reliability, security, maintainability (flexibility), safety, and
   operability. Ask for a short description per category or topic.
2. Scenarios. Which requirements need a concrete scenario to become testable?
   Two kinds are especially useful:
   - usage scenarios: the runtime reaction of the system to a stimulus,
     including efficiency and performance, for example "the system answers a
     user request within one second"
   - change scenarios: the desired effect of a modification or extension of the
     system or its environment, measured in effort or duration Also consider
     fault, error and failure scenarios.
3. Per scenario, short form: context or background, source and stimulus, and a
   metric or acceptance criterion. Long form, if the user prefers it: scenario
   ID, name, source, stimulus, environment, artifact, response and response
   measure. Push back on vague statements such as "fast" or "secure" until there
   is a measurable criterion.

## Step 2: Draft the Section

Produce the section in the arc42 form below. A table is the default for 10.1; a
mind map or quality attribute tree is an alternative.

```markdown
# 10. Quality Requirements

The quality goals of highest priority are in Section 1.2.

## 10.1 Quality Requirements Overview

| Category/Topic | Quality Requirement                    |
| -------------- | -------------------------------------- |
| [Category]     | [Short description of the requirement] |

## 10.2 Quality Scenarios

| Context/Background | Source/Stimulus           | Metric/Acceptance Criteria |
| ------------------ | ------------------------- | -------------------------- |
| [Situation]        | [Who or what triggers it] | [Measurable response]      |
```

Long form, one table per scenario or one row per scenario:

```markdown
| ID   | Name   | Source   | Stimulus  | Environment | Artifact         | Response   | Response Measure |
| ---- | ------ | -------- | --------- | ----------- | ---------------- | ---------- | ---------------- |
| [ID] | [Name] | [Source] | [Trigger] | [Condition] | [Building block] | [Reaction] | [Metric]         |
```

## Step 3: Review and Iterate

Check the draft against the arc42 guidance. For every failed item, explain what
is wrong and how to fix it.

- Are the quality goals of Section 1.2 referenced rather than repeated?
- Does the overview summarize by category or topic?
- Is every scenario specific and measurable, with a metric or acceptance
  criterion?
- Were both usage and change scenarios considered, and fault scenarios where
  relevant?
- If 10.2 is omitted, is 10.1 precise enough to serve as acceptance criteria?

Cross-section consistency, where the sections exist:

- Scenarios can be used to evaluate the decisions in Sections 4 and 9.
- Artifacts named in scenarios are building blocks from Section 5.
- Quality requirements that are at risk appear in Section 11.

Then ask what the user wants to refine and iterate until they are satisfied.

Based on <https://docs.arc42.org/section-10/>, the arc42 template by Dr. Gernot
Starke and Dr. Peter Hruschka (CC BY-SA 4.0), and Bass, Clements, Kazman,
Software Architecture in Practice, 4th edition (2021).
