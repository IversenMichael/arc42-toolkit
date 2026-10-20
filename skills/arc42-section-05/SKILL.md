---
name: arc42-section-05
version: 2.0.0
description:
  Interactively guides the documentation of arc42 Section 5 (Building Block
  View) in the form of the official arc42 template. Asks about the level 1
  decomposition, black boxes, interfaces and source code mapping before drafting
  the white box and black box descriptions, then iterates until the user is
  satisfied.
---

# arc42 Section 5: Building Block View

You help document Section 5 of an arc42 architecture documentation. Follow the
official template at <https://docs.arc42.org/section-5/>.

Section 5 shows the static decomposition of the system into building blocks
(modules, components, subsystems, classes, interfaces, packages, libraries,
frameworks, layers, partitions, tiers, functions, macros, operations, data
structures, and so on) and their dependencies. arc42 calls this view mandatory
for every architecture documentation; it is the floor plan of the system. Its
purpose is an overview of the source code through abstraction, so that the
structure can be discussed with stakeholders without implementation details.

The view is a hierarchy of white boxes and black boxes:

- Level 1 is the white box description of the overall system with black box
  descriptions of all contained building blocks.
- Level 2 zooms into selected building blocks of level 1 and describes them as
  white boxes, with black box descriptions of their inner building blocks.
- Level 3 zooms into selected building blocks of level 2, and so on.

## Step 1: Ask Before Writing

Do not draft anything until the questions below are answered.

First read Section 3 (the external interfaces must reappear at level 1) and
Section 4 (the decomposition must match the solution strategy) if they exist.
Also read Sections 6 and 7 if they exist, because they use the building block
names from here.

1. Level 1 building blocks. Which building blocks does the overall system
   consist of? For each: its name and its purpose or responsibility in one or
   two sentences. Cohesion should be the primary driver of the decomposition.
2. Motivation. Why was the system decomposed this way? Which criteria were used?
3. Interfaces. Which interfaces exist between the level 1 building blocks and to
   the outside? Which of them are important enough to describe separately?
   Examples or simple signatures are often enough.
4. Black box details. For each building block: its interfaces, and optionally
   quality or performance characteristics, the directory or file location of its
   source code, the requirements it fulfils, and open issues, problems or risks.
   Every piece of source code should be locatable in some building block; align
   the mapping with the directory structure and the modularization constructs of
   the programming language.
5. Third-party software. Are there third-party components that stakeholders need
   to see in the view? Mark them clearly.
6. Deeper levels. Which level 1 building blocks are important, surprising,
   risky, complex or volatile enough to justify a white box description at level
   2? Prefer relevance over completeness and leave out normal, simple, boring or
   standardized parts. Repeat the question for level 3 where needed.

## Step 2: Draft the Section

Produce the section in the arc42 form below. Use any notation for the diagrams;
arc42 prescribes none. If you generate a diagram as text, such as PlantUML,
store it in its own file and reference it from the section.

The white box template consists of an overview diagram, the motivation for the
decomposition, black box descriptions of the contained building blocks (as one
table, or as one black box template each), and optionally important interfaces.
The black box template consists of purpose or responsibility, interfaces, and
optionally quality or performance characteristics, directory or file location,
fulfilled requirements, and open issues, problems or risks.

```markdown
# 5. Building Block View

## 5.1 Whitebox Overall System

[Overview diagram of the overall system and its level 1 building blocks.]

Motivation: [Why the system is decomposed this way.]

Contained building blocks:

| Name      | Responsibility                | Interfaces         | Code       |
| --------- | ----------------------------- | ------------------ | ---------- |
| [Block 1] | [Purpose in one or two lines] | [Major interfaces] | [Location] |
| [Block 2] | [Purpose in one or two lines] | [Major interfaces] | [Location] |

Important interfaces: [Interfaces that are important for understanding the white
box and are not covered in a black box description.]

### 5.1.1 [Name of Black Box 1]

Purpose/Responsibility: [What the building block does and is responsible for.]

Interface(s): [Provided and required interfaces, including qualities and
performance characteristics where relevant.]

Quality/Performance Characteristics: [Optional.]

Directory/File Location: [Optional.]

Fulfilled Requirements: [Optional, for traceability.]

Open Issues/Problems/Risks: [Optional.]

### 5.1.2 [Name of Black Box 2]

[Black box template.]

## 5.2 Level 2

### 5.2.1 White Box [Building Block 1]

[White box template: overview diagram, motivation, contained black boxes,
important interfaces.]

## 5.3 Level 3

### 5.3.1 White Box [Building Block 1.1]

[White box template.]
```

The Interfaces and Code columns of the table are optional. When the table is
enough, omit the per-block black box subsections. Omit 5.2 and 5.3 when no
building block needs refinement.

## Step 3: Review and Iterate

Check the draft against the arc42 guidance. For every failed item, explain what
is wrong and how to fix it.

Level 1:

- Is the level 1 white box present with a diagram, a motivation and black box
  descriptions of all contained building blocks?
- Do the external interfaces at level 1 match the communication partners in
  Section 3?
- Does every important black box state its responsibility or purpose?
- Are the inner workings of black boxes hidden? Internals belong to the next
  level.
- Is it explained where the source code of each building block lives, and can
  every piece of source code be assigned to a building block?
- Are third-party elements clearly marked?

Deeper levels:

- Is every white box structure justified by a motivation?
- Are only a few, relevant building blocks refined, and are the lower-level
  blocks clearly traceable to their parent?
- Are building blocks refined consistently, so that each lower level uses the
  same template?

Cross-section consistency, where the sections exist:

- The decomposition matches Section 4.
- Section 6 scenarios and Section 7 deployment use the building block names from
  here.
- Similarities across building blocks are described once in Section 8 rather
  than repeated per block.

Then ask what the user wants to refine and iterate until they are satisfied.

Based on <https://docs.arc42.org/section-5/> and the arc42 template by Dr. Gernot
Starke and Dr. Peter Hruschka (CC BY-SA 4.0).
