---
name: arc42-section-03
version: 2.0.0
description:
  Interactively guides the documentation of arc42 Section 3 (Context and Scope)
  in the form of the official arc42 template. Asks about communication partners,
  domain inputs and outputs, and channels before drafting the business and
  technical context, then iterates until the user is satisfied.
---

# arc42 Section 3: Context and Scope

You help document Section 3 of an arc42 architecture documentation. Follow the
official template at <https://docs.arc42.org/section-3/>.

Section 3 delimits the system (the scope) from all its communication partners,
that is neighbouring systems and users (the context), and thereby specifies the
external interfaces. Where necessary it differentiates the business context
(domain-specific inputs and outputs) from the technical context (channels,
protocols, hardware). The domain and technical interfaces to communication
partners are among the most critical aspects of a system.

## Step 1: Ask Before Writing

Do not draft anything until the questions below are answered.

First check which other sections exist. Section 5 Level 1 must show the same
external interfaces as this section, and Section 7 is where a detailed technical
context may be deferred to.

1. System name. What is the system called? It appears as one black box.
2. Communication partners. Which users and roles, and which neighbouring
   systems, exchange anything with the system? Ask for all of them, including
   scheduled jobs, monitoring, data imports and exports, and external influences
   such as regulations. If there are many partners, ask for criteria to cluster
   them.
3. Domain inputs and outputs. For each partner: which domain-specific data or
   events go into the system and which come out? Optionally domain-specific
   formats or protocols. Ask for data flows, not dependencies.
4. Technical context. Is a technical context needed? It is when hardware,
   channels or protocols are central to the system or decided by infrastructure
   stakeholders. If so: for each partner, which channel or transmission medium
   (network, protocol, device, file transfer) carries the inputs and outputs?
   Otherwise the technical details may be deferred to Section 7.
5. Risks and quality requirements at the interfaces. Are there interfaces with
   known problems, or quality requirements that only apply at one interface?

## Step 2: Draft the Section

Produce the section in the arc42 form: a context diagram that shows the system
as a black box, and a table of communication partners with their inputs and
outputs. Use any notation the stakeholders read; arc42 prescribes none. If you
generate a diagram as text, such as PlantUML, store it in its own file and
reference it from the section.

```markdown
# 3. Context and Scope

## 3.1 Business Context

[Diagram: the system as a single black box, its communication partners, and the
domain-specific inputs and outputs between them.]

[System name]

| Communication Partner | Inputs              | Outputs              |
| --------------------- | ------------------- | -------------------- |
| [User or system]      | [Data or events in] | [Data or events out] |

[Optional: explanation of the external domain interfaces.]

## 3.2 Technical Context

[Diagram, for example a UML deployment diagram, showing the channels and
transmission media that link the system to its environment.]

[Optional: explanation of the technical interfaces.]

Mapping of input and output to channels:

| Input/Output | Channel                    |
| ------------ | -------------------------- |
| [I/O]        | [Protocol, medium, device] |
```

Leave out 3.2 when no technical context is needed.

## Step 3: Review and Iterate

Check the draft against the arc42 guidance. For every failed item, explain what
is wrong and how to fix it.

Business context:

- Is the system shown as one black box without internal building blocks? Those
  belong in Section 5.
- Are all communication partners shown? Missing partners mean missing
  interfaces.
- Does the diagram come with a table of partners, inputs and outputs?
- Does the business context show data flows rather than technical details?
- Is the context an overview? Details of each interface do not belong here.

Technical context, when present:

- Are channels, transmission media and protocols named?
- Is every domain input and output mapped to a channel?
- Would the stakeholders be better served by deferring these details to the
  deployment view in Section 7?

Cross-section consistency, where the sections exist:

- The external interfaces of Section 5 Level 1 must match the partners here.
- Section 6 runtime scenarios may only involve partners that appear here.
- Section 7 zooms into the infrastructure shown as one black box in 3.2.

Then ask what the user wants to refine and iterate until they are satisfied.

Based on <https://docs.arc42.org/section-3/> and the arc42 template by Dr. Gernot
Starke and Dr. Peter Hruschka (CC BY-SA 4.0).
