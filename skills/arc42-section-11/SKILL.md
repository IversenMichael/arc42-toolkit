---
name: arc42-section-11
version: 2.0.0
description:
  Interactively guides the documentation of arc42 Section 11 (Risks and
  Technical Debts) in the form of the official arc42 template. Searches for
  risks and debts with stakeholders and in interfaces, processes, data and
  source code, then drafts a prioritized list with suggested measures and
  iterates until the user is satisfied.
---

# arc42 Section 11: Risks and Technical Debts

You help document Section 11 of an arc42 architecture documentation. Follow the
official template at <https://docs.arc42.org/section-11/>.

Section 11 is a list of identified technical risks and technical debts, ordered
by priority, probably including suggested measures to minimize, mitigate or
avoid risks or to reduce technical debts. "Risk management is project management
for grown-ups" (Tim Lister). Management stakeholders such as project managers
and product owners need this list for the overall risk analysis and measurement
planning.

## Step 1: Ask Before Writing

Do not draft anything until the questions below are answered.

First read Section 9 (decisions with negative consequences), Section 10 (quality
requirements at risk), Section 3 (external interfaces) and Section 5 (building
blocks) if they exist, and collect candidates from them.

1. Stakeholders. Which problems and risks do different stakeholders see? Ask the
   user to name what developers, operations, product owners and management worry
   about.
2. External interfaces. Which interfaces in Section 3 are fragile, unclear, out
   of the team's control or badly specified?
3. Qualitative evaluation. Has an evaluation such as ATAM been done, or can the
   quality scenarios in Section 10 be walked through to find where the
   architecture does not meet them?
4. Processes. Which development, deployment or operation processes carry risks?
5. Data. Which data or data structures are problematic, for example
   inconsistent, unowned, unmigrated or large?
6. Source code. Which parts of the code are known to be problematic: complex,
   untested, outdated, duplicated?
7. Per item: is it a risk (something that may go wrong) or a technical debt
   (something known to be wrong)? What is its priority? Which measures are
   suggested to minimize, mitigate or avoid the risk, or to reduce the debt?

## Step 2: Draft the Section

Produce the section in the arc42 form: a list or table ordered by priority.

```markdown
# 11. Risks and Technical Debts

| Priority | Risk or Debt | Description                          | Suggested Measures                  |
| -------- | ------------ | ------------------------------------ | ----------------------------------- |
| 1        | [Title]      | [What may go wrong or what is wrong] | [Minimize, mitigate, avoid, reduce] |
| 2        | [Title]      | [Description]                        | [Measures]                          |
```

Separate tables for risks and for technical debts are fine when the lists are
long.

## Step 3: Review and Iterate

Check the draft against the arc42 guidance. For every failed item, explain what
is wrong and how to fix it.

- Is the list ordered by priority?
- Does every entry describe the problem clearly enough for a manager to include
  it in the overall risk analysis?
- Does every entry suggest measures, or state explicitly that none are planned?
- Were all sources searched: stakeholders, external interfaces, qualitative
  evaluation, processes, data, source code?
- Is anything the team worries about missing?

Cross-section consistency, where the sections exist:

- Negative consequences of decisions in Section 9 that remain open appear here.
- Quality requirements in Section 10 that the architecture does not meet appear
  here.
- Interfaces and building blocks are named as in Sections 3 and 5.

Then ask what the user wants to refine and iterate until they are satisfied.

Based on <https://docs.arc42.org/section-11/> and the arc42 template by Dr. Gernot
Starke and Dr. Peter Hruschka (CC BY-SA 4.0).
