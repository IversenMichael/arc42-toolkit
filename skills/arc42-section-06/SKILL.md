---
name: arc42-section-06
version: 2.0.0
description:
  Interactively guides the documentation of arc42 Section 6 (Runtime View) in
  the form of the official arc42 template. Asks for a representative selection
  of architecturally relevant scenarios and the building blocks involved before
  drafting them in a suitable notation, then iterates until the user is
  satisfied.
---

# arc42 Section 6: Runtime View

You help document Section 6 of an arc42 architecture documentation. Follow the
official template at <https://docs.arc42.org/section-6/>.

Section 6 describes the concrete behaviour and interactions of the building
blocks in the form of scenarios from these areas:

- important use cases or features: how do the building blocks execute them?
- interactions at critical external interfaces: how do the building blocks
  cooperate with users and neighbouring systems?
- operation and administration: launch, start-up, stop
- error and exception scenarios

The main criterion for choosing scenarios is their architectural relevance. A
representative selection is enough; a large number of scenarios is not the goal.
Scenarios mainly serve stakeholders who are less willing or able to read the
static models in Sections 5 and 7.

## Step 1: Ask Before Writing

Do not draft anything until the questions below are answered.

First read Section 5 (scenarios refer to its building blocks) and Section 3
(scenarios refer to its communication partners) if they exist.

1. Scenario candidates. Go through the four areas above and ask which scenarios
   are architecturally relevant: they show how an important feature is executed,
   how a critical external interface is served, how the system starts, stops or
   is administered, or how an important error is handled.
2. Selection. Which few scenarios are representative? Drop the rest.
3. Per scenario: which building blocks from Section 5 and which communication
   partners from Section 3 take part, in which order do they interact, and what
   is notable about the interaction? Should the scenario be schematic or
   detailed? Schematic is the default; detailed scenarios are costly to
   maintain.
4. Notation. Which notation do the stakeholders read? arc42 suggests numbered
   steps in natural language, activity diagrams or flow charts, sequence
   diagrams, BPMN or event process chains, and state machines.

## Step 2: Draft the Section

Produce one subsection per scenario in the arc42 form below. Every activity in a
scenario must be attributed to an existing building block. If you generate a
diagram as text, such as PlantUML, store it in its own file and reference it
from the section.

```markdown
# 6. Runtime View

## 6.1 [Runtime Scenario 1]

[Runtime diagram, or a textual description such as a numbered list of steps,
each naming the building block that performs it.]

1. [Partner or building block] [does something] with [building block]
2. [Building block] [does something]
3. ...

[Description of the notable aspects of the interactions between the building
block instances shown above.]

## 6.2 [Runtime Scenario 2]

[Same structure.]
```

## Step 3: Review and Iterate

Check the draft against the arc42 guidance. For every failed item, explain what
is wrong and how to fix it.

- Is every scenario architecturally relevant, and is the set a small,
  representative selection rather than an exhaustive list?
- Is every activity mapped to a building block that exists in Section 5?
- Do external participants exist as communication partners in Section 3?
- Are scenarios schematic unless there is a reason for detail?
- Does each scenario explain what is notable about the interaction, not only
  list the steps?
- Were the four areas considered, so that operation and error scenarios are not
  forgotten when they matter?

Then ask what the user wants to refine and iterate until they are satisfied.

Based on <https://docs.arc42.org/section-6/> and the arc42 template by Dr. Gernot
Starke and Dr. Peter Hruschka (CC BY-SA 4.0).
