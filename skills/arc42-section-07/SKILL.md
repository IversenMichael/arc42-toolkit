---
name: arc42-section-07
version: 2.0.0
description:
  Interactively guides the documentation of arc42 Section 7 (Deployment View) in
  the form of the official arc42 template. Asks about the technical
  infrastructure, the environments and the mapping of building blocks to
  infrastructure before drafting Infrastructure Level 1 and Level 2, then
  iterates until the user is satisfied.
---

# arc42 Section 7: Deployment View

You help document Section 7 of an arc42 architecture documentation. Follow the
official template at <https://docs.arc42.org/section-7/>.

Section 7 describes:

1. the technical infrastructure used to execute the system, with elements such
   as geographical locations, environments, computers, processors, channels and
   network topologies
2. the mapping of the software building blocks to those infrastructure elements

Document all relevant environments, for example development, test and
production. The view matters most for distributed systems with more than one
computer, processor, server or container, and for self-built hardware. From a
software perspective it is sufficient to capture the infrastructure elements
needed to show the deployment of the building blocks; hardware architects may go
deeper.

## Step 1: Ask Before Writing

Do not draft anything until the questions below are answered.

First read Section 5 (every building block must be mapped to infrastructure),
Section 3.2 (this section zooms into the infrastructure shown there as one black
box) and Section 2 (infrastructure constraints) if they exist.

1. Environments. Which environments exist, and which of them are relevant to
   document?
2. Infrastructure level 1. Per environment: how is the system distributed over
   locations, environments, computers, processors and containers, and what are
   the physical connections between them? Explain every node.
3. Motivation. Why this deployment structure? Which hardware and infrastructure
   decisions were taken, and why? Leave hardware decisions themselves to
   hardware experts; record them here.
4. Quality and performance features. Which qualities does the infrastructure
   provide or limit (availability, throughput, latency, capacity)?
5. Mapping. Which building blocks from Section 5 run on which infrastructure
   element? A table is often enough.
6. Infrastructure level 2. Which infrastructure elements of level 1 need their
   own internal structure documented?
7. Operation. What else is relevant for running the system: installation,
   configuration, monitoring, backup, administration?

## Step 2: Draft the Section

Produce the section in the arc42 form below. arc42 suggests UML deployment
diagrams, possibly nested, but any notation that shows nodes and channels is
fine. If you generate a diagram as text, such as PlantUML, store it in its own
file and reference it from the section.

```markdown
# 7. Deployment View

## 7.1 Infrastructure Level 1

[Overview diagram of the infrastructure and the deployed building blocks.]

Motivation: [Why this deployment structure; the hardware and infrastructure
decisions behind it.]

Quality and/or Performance Features: [What the infrastructure provides or
limits.]

Mapping of Building Blocks to Infrastructure:

| Building Block | Infrastructure Element |
| -------------- | ---------------------- |
| [Block]        | [Node, container, ...] |

## 7.2 Infrastructure Level 2

### 7.2.1 [Infrastructure Element 1]

[Diagram and explanation of the internal structure of the element, using the
same structure as level 1.]
```

For multiple environments or alternative deployments, repeat the level 1
structure once per environment, for example as 7.1.1 Production and 7.1.2 Test.
Omit 7.2 when no element needs refinement.

## Step 3: Review and Iterate

Check the draft against the arc42 guidance. For every failed item, explain what
is wrong and how to fix it.

- Are all relevant environments documented?
- Does level 1 contain a diagram, a motivation, the quality or performance
  features and the mapping of building blocks?
- Is every building block from Section 5 mapped to an infrastructure element?
- Is every node explained, and are hardware and infrastructure decisions
  justified?
- Is the level of detail limited to what is needed to show the deployment?
- Is the view hierarchical, with level 2 only for elements that need it?
- Is what matters for operation of the system covered?

Cross-section consistency, where the sections exist:

- The infrastructure refines the black box of Section 3.2.
- Infrastructure choices respect the constraints in Section 2.
- Building block names match Section 5.

Then ask what the user wants to refine and iterate until they are satisfied.

Based on <https://docs.arc42.org/section-7/> and the arc42 template by Dr. Gernot
Starke and Dr. Peter Hruschka (CC BY-SA 4.0).
