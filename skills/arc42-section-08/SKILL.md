---
name: arc42-section-08
version: 2.0.0
description:
  Interactively guides the documentation of arc42 Section 8 (Cross-cutting
  Concepts) in the form of the official arc42 template. Uses the arc42 concept
  topics as a checklist to pick only the concepts the system needs, asks how
  each works, and drafts one subsection per concept, then iterates until the
  user is satisfied.
---

# arc42 Section 8: Cross-cutting Concepts

You help document Section 8 of an arc42 architecture documentation. Follow the
official template at <https://docs.arc42.org/section-8/>.

Section 8 describes cross-cutting concepts: practices, patterns, regulations or
solution ideas that relate to several building blocks, hardware elements or
development processes. Concepts are the basis for conceptual integrity, that is
consistency and homogeneity, of the architecture. Documenting a concept once
centrally is easier than repeating it in every affected building block.

Pick only the most needed topics for the system and give each its own level 2
heading (8.1, 8.2, ...). Do not attempt to cover every possible topic.

## Step 1: Ask Before Writing

Do not draft anything until the questions below are answered.

First read Section 5 (concepts refer to building blocks), Section 4 (the
strategy may announce concepts) and Section 1.2 (quality goals often need a
concept) if they exist.

1. Candidate topics. Walk through the arc42 collection of concept topics and ask
   which of them matter for this system:
   - domain concepts: domain model, business rules, data model
   - user experience: user interface, ergonomics, internationalization
   - safety and security
   - architecture and design patterns
   - under the hood: persistence, transaction handling, session handling,
     exception and error handling, logging, communication and integration,
     concurrency, caching, parallelization, plausibility and validity checks
   - development concepts: build, test, configuration, migration, integration,
     code generation
   - operational concepts: administration, monitoring, disaster recovery,
     scaling, clustering
2. Selection. Which of the candidates are really needed? arc42 recommends
   documenting at least the domain or business data model.
3. Per concept: how does it work, concretely? Which building blocks, hardware
   elements or processes does it concern? Which form suits it best: a concept
   paper, an example implementation with source code or tests, or a model
   excerpt or scenario in the notation of the architecture views?
4. Decisions instead of concepts. Would some topics be better recorded as a
   decision in Section 9 than as a concept?

## Step 2: Draft the Section

Produce one level 2 subsection per chosen concept. The form may vary per
concept. If you generate a diagram as text, such as PlantUML, store it in its
own file and reference it from the section.

```markdown
# 8. Cross-cutting Concepts

## 8.1 [Concept 1]

[Explanation of how the concept works: the approach, rule, principle, tactic or
strategy; a model excerpt, example implementation or diagram where that explains
it best; and the building blocks it applies to.]

## 8.2 [Concept 2]

[Explanation.]
```

## Step 3: Review and Iterate

Check the draft against the arc42 guidance. For every failed item, explain what
is wrong and how to fix it.

- Are only the most needed topics documented? Remove generic text that does not
  say anything specific about this system.
- Does every concept explain how it works, not only that it exists?
- Is it clear which building blocks each concept applies to, with links in both
  directions where possible?
- Is the domain or business data model documented, or was it consciously left
  out?
- Is the glossary in Section 12 consistent with the domain model?
- Would any concept be better documented as a decision in Section 9?

Cross-section consistency, where the sections exist:

- Concepts match the solution strategy in Section 4.
- Building block names match Section 5.

Then ask what the user wants to refine and iterate until they are satisfied.

Based on <https://docs.arc42.org/section-8/> and the arc42 template by Dr. Gernot
Starke and Dr. Peter Hruschka (CC BY-SA 4.0).
