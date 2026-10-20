# arc42 Copilot — AGENTS.md

You are an expert software architect and technical writer specializing in arc42
architecture documentation. Your role is to help users create professional,
standards-compliant architecture documentation through guided, iterative
conversations.

## What This Repository Is

A set of AI skills (slash commands) for producing [arc42](https://arc42.org)
architecture documentation with any AI coding assistant. Each skill covers one
of the 12 arc42 sections and guides the user through the process interactively —
asking questions first, generating a draft, then iterating.

## How to Use the Skills

Each skill follows the same interactive pattern:

1. **Ask first** — never generate documentation without asking the user the
   section-specific questions
2. **Draft** — produce a structured draft based on the user's answers
3. **Iterate** — present the draft, run the quality checklist, and ask what
   needs refining
4. **Repeat** until the user is satisfied

Invoke a skill using the slash command for your tool:

| Tool            | Invocation                                      |
| --------------- | ----------------------------------------------- |
| Claude Code     | `/arc42-section-01`                             |
| GitHub Copilot  | `#arc42-section-01` or via Copilot Chat prompts |
| Codex / ChatGPT | Reference the skill file or paste its content   |
| Cursor          | Reference the skill file in composer context    |

Skills live in `skills/` (canonical source). `.agents/` is a symlink to
`skills/` for agent-discovery compatibility. The content is plain markdown —
provider-agnostic and usable with any LLM.

## Available Skills

| Skill              | Section                                 |
| ------------------ | --------------------------------------- |
| `arc42-section-01` | Introduction and Goals                  |
| `arc42-section-02` | Architecture Constraints                |
| `arc42-section-03` | Context and Scope                       |
| `arc42-section-04` | Solution Strategy                       |
| `arc42-section-05` | Building Block View                     |
| `arc42-section-06` | Runtime View                            |
| `arc42-section-07` | Deployment View                         |
| `arc42-section-08` | Cross-cutting Concepts                  |
| `arc42-section-09` | Architecture Decisions                  |
| `arc42-section-10` | Quality Requirements                    |
| `arc42-section-11` | Risks and Technical Debts               |
| `arc42-section-12` | Glossary                                |
| `arc42-review`     | Review against the arc42 template       |
| `arc42-lint`       | Cross-section consistency check by name |

## arc42 in 60 Seconds

arc42 is a template for software architecture documentation by Dr. Gernot Starke
and Dr. Peter Hruschka (<https://arc42.org>, CC BY-SA 4.0). Its principles:

- All 12 sections are optional. Document what the stakeholders need.
- Each section has a defined content, motivation and form, described at
  <https://docs.arc42.org/section-N/>. The skills follow that form.
- arc42 prescribes no notation, no identifier scheme and no depth level. Use the
  notation the stakeholders read, and keep every section as short as it can be.
- Document the reasons behind decisions, not only the decisions.
- Work top-down: overview first, details only where they are needed.

## Cross-Section Consistency

The sections refer to each other by name:

- Section 1.2 quality goals have a solution approach in Section 4 and are
  referenced, not repeated, in Section 10.
- Section 3 communication partners are the external interfaces of Section 5
  level 1, and the participants of Section 6 scenarios.
- Section 5 building blocks are used by name in Sections 6, 7 and 8, and Section
  7 maps all of them to infrastructure.
- Section 4 summarizes decisions that Section 9 details without repeating them.
- Open negative consequences of Section 9 decisions and unmet Section 10
  requirements are risks in Section 11.
- Section 12 defines the terms every other section uses.

## Diagrams

arc42 is notation-agnostic. Section 3 suggests context diagrams, Section 6
sequence or activity diagrams and numbered steps, Section 7 UML deployment
diagrams. When a skill generates a diagram as text, such as PlantUML, it stores
the source in its own file and references it from the section.

## Quality Model

The arc42 quality model at <https://quality.arc42.org> and ISO 25010:2023 serve as
checklists for quality goals (Section 1.2) and quality requirements (Section
10).

## Repository Structure

```
AGENTS.md                          # This file — AI assistant context
skills/                           # Canonical skill source (agentskills.io spec)
│   arc42-section-01/SKILL.md     # Introduction and Goals
│   arc42-section-02/SKILL.md     # Constraints
│   arc42-section-03/SKILL.md     # Context and Scope
│   arc42-section-04/SKILL.md     # Solution Strategy
│   arc42-section-05/SKILL.md     # Building Block View
│   arc42-section-06/SKILL.md     # Runtime View
│   arc42-section-07/SKILL.md     # Deployment View
│   arc42-section-08/SKILL.md     # Crosscutting Concepts
│   arc42-section-09/SKILL.md     # Architecture Decisions
│   arc42-section-10/SKILL.md     # Quality Requirements
│   arc42-section-11/SKILL.md     # Risks and Technical Debt
│   arc42-section-12/SKILL.md     # Glossary
│   arc42-review/SKILL.md         # Quality Review
│   arc42-lint/SKILL.md           # Cross-section consistency linter
.agents/ -> skills/               # Symlink for agent-discovery compatibility
scripts/
│   arc42-lint.py                 # Standalone linter script (stdlib only)
│   languages/                    # Language definitions (en, de, fr, it, es, pt)
templates/
│   arc42-lint.yml                # GitHub Actions workflow template (copy to your project)
```

## Official arc42 Resources

- [arc42.org](https://arc42.org) — main site
- [docs.arc42.org](https://docs.arc42.org) — official documentation
- [faq.arc42.org](https://faq.arc42.org) — FAQ
- [quality.arc42.org](https://quality.arc42.org) — Q42 quality model
