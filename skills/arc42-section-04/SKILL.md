---
name: arc42-section-04
version: 2.0.0
description:
  Interactively guides the documentation of arc42 Section 4 (Solution Strategy)
  in the form of the official arc42 template. Asks about technology decisions,
  top-level decomposition, approaches to the quality goals and organizational
  decisions before drafting a short summary, then iterates until the user is
  satisfied.
---

# arc42 Section 4: Solution Strategy

You help document Section 4 of an arc42 architecture documentation. Follow the
official template at <https://docs.arc42.org/section-4/>.

Section 4 is a short summary and explanation of the fundamental decisions and
solution strategies that shape the architecture:

- technology decisions
- decisions about the top-level decomposition, for example an architectural or
  design pattern
- decisions on how to achieve the key quality goals
- relevant organizational decisions, for example the development process or
  delegating tasks to third parties

These decisions are the cornerstones of the architecture and the basis for many
detailed decisions. Keep the section short and refer to the later sections for
details.

## Step 1: Ask Before Writing

Do not draft anything until the questions below are answered.

First read Section 1.2 (quality goals) and Section 2 (constraints) if they
exist. Ask for the top quality goals if Section 1.2 does not exist yet.

1. Technology decisions. Which fundamental technologies were chosen (languages,
   frameworks, platforms, databases, middleware)? Why, given the problem, the
   quality goals and the constraints?
2. Top-level decomposition. How is the system structured at the top level and
   which architectural or design patterns shape it? Why?
3. Quality goals. For each key quality goal: which scenario illustrates it, and
   which solution approach achieves it? Where are the details (Section 5 for
   structure, Section 8 for concepts, Section 9 for decisions)?
4. Organizational decisions. Which decisions about the development process, team
   organization or third parties shape the architecture?

Accept that the strategy may be incomplete; it grows iteratively.

## Step 2: Draft the Section

Produce the section in the arc42 form: a compact list of the key decisions with
their motivation, and a table that connects quality goals to solution
approaches. Subheadings are optional.

```markdown
# 4. Solution Strategy

[Short list of the fundamental decisions, each with why it was taken, based on
the problem statement, the quality goals and the key constraints.]

- Technology: [decision and why]
- Decomposition: [pattern or structure and why], see Section 5
- Organization: [process or sourcing decision and why]

| Quality Goal | Scenario   | Solution Approach | Link to Details          |
| ------------ | ---------- | ----------------- | ------------------------ |
| [Goal 1]     | [Scenario] | [Approach]        | [Section 5, 8 or 9 item] |
| [Goal 2]     | [Scenario] | [Approach]        | [Section 5, 8 or 9 item] |
```

## Step 3: Review and Iterate

Check the draft against the arc42 guidance. For every failed item, explain what
is wrong and how to fix it.

- Is the section short? A list of keywords or a one-page table is the goal.
- Is every decision justified in terms of the problem, the quality goals and the
  constraints?
- Are all four areas considered: technology, decomposition, quality goals,
  organization?
- Does every quality goal from Section 1.2 have a solution approach?
- Does the section refer to Sections 5, 8 and 9 for details instead of repeating
  them?

Cross-section consistency, where the sections exist:

- No decision may violate a constraint in Section 2.
- The decomposition must match Section 5 Level 1.
- Decisions detailed in Section 9 are only summarized here, not repeated.

Then ask what the user wants to refine and iterate until they are satisfied.

Based on <https://docs.arc42.org/section-4/> and the arc42 template by Dr. Gernot
Starke and Dr. Peter Hruschka (CC BY-SA 4.0).
