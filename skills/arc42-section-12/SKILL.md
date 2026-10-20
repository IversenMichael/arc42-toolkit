---
name: arc42-section-12
version: 2.0.0
description:
  Interactively guides the documentation of arc42 Section 12 (Glossary) in the
  form of the official arc42 template. Collects the domain and technical terms
  the stakeholders use, resolves synonyms and homonyms, and drafts a compact
  term and definition table, then iterates until the user is satisfied.
---

# arc42 Section 12: Glossary

You help document Section 12 of an arc42 architecture documentation. Follow the
official template at <https://docs.arc42.org/section-12/>.

Section 12 defines the most important domain and technical terms that the
stakeholders use when discussing the system, so that all stakeholders have an
identical understanding of these terms and do not use synonyms and homonyms. In
multi-language environments the glossary also serves as the source for
translations.

## Step 1: Ask Before Writing

Do not draft anything until the questions below are answered.

First scan the existing sections for terms that are used without definition:
communication partners in Section 3, building blocks in Section 5, concepts and
domain model entities in Section 8, and decisions in Section 9. Present the
candidates to the user.

1. Domain terms. Which business terms do the stakeholders use, and what do they
   mean for this system?
2. Technical terms. Which technical terms and abbreviations need a definition
   for the stakeholders of this documentation? Skip trivia that every reader
   knows.
3. Synonyms and homonyms. Are there concepts with several names, or names with
   several meanings? Agree on one preferred term per concept and one meaning per
   term, and note the alternatives in the definition.
4. Translations. Does the team work in several languages? If so, which languages
   need a column?
5. Model. Would a graphical model, such as the domain model in Section 8, help
   to explain how the terms relate?

## Step 2: Draft the Section

Produce the section in the arc42 form: a single table with the columns Term and
Definition, and additional columns for translations when needed. Sort the terms
alphabetically.

```markdown
# 12. Glossary

| Term   | Definition                                          |
| ------ | --------------------------------------------------- |
| [Term] | [Meaning in this system; synonyms to avoid, if any] |
| [Term] | [Definition]                                        |
```

With translations:

```markdown
| Term   | Definition   | [Language 2] |
| ------ | ------------ | ------------ |
| [Term] | [Definition] | [Term]       |
```

## Step 3: Review and Iterate

Check the draft against the arc42 guidance. For every failed item, explain what
is wrong and how to fix it.

- Is the glossary compact and free of trivia?
- Does every definition say what the term means for this system?
- Is every synonym resolved to one preferred term, and every homonym to one
  meaning?
- Are the terms used consistently in the other sections? Flag deviations.
- Are the terms used in Sections 3, 5, 8 and 9 covered where they need
  explanation?
- Is the glossary consistent with the domain model in Section 8?
- Is it clear who maintains the glossary? arc42 suggests the product owner or
  project manager.

Then ask what the user wants to refine and iterate until they are satisfied.

Based on <https://docs.arc42.org/section-12/> and the arc42 template by Dr. Gernot
Starke and Dr. Peter Hruschka (CC BY-SA 4.0).
