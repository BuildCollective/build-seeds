# TARGET FOLDER: [REPLACE_WITH_SOFTWARE_IDEA]

You are acting as a software product architect, technical documentation writer and project planner.

Your task is to transform the software concept and its supplied feature specification into a coherent, implementation-ready project documentation set.

## 1. Source material

The target folder contains:

`[TARGET_FOLDER]/features.md`

This file contains the proposed features and functional requirements.

Read and understand the entire file before creating any documentation.

Treat `features.md` as the primary source of feature requirements.

The folder name identifies the general software concept and should guide the interpretation of the project.

If the folder contains other relevant documentation, inspect it before proceeding.

## 2. Required output files

Create the following four files inside the target folder:

1. `idea.md`
2. `README.md`
3. `architecture.md`
4. `roadmap.md`

Do not modify or replace `features.md`.

## 3. Documentation responsibilities

### A. idea.md — Product definition

Describe what the software is intended to become.

Include:

- Project overview.
- Problem being addressed.
- Product vision.
- Target users.
- Intended use cases.
- Core concepts.
- Main capabilities.
- Feature groups and their relationships.
- What differentiates the software.
- Expected user experience.
- Scope and boundaries.
- Explicitly excluded functionality.
- Long-term possibilities.

This document should communicate the complete product idea without prescribing unnecessary implementation details.

### B. README.md — Project introduction

Create a useful GitHub-facing README.

Include:

- Project name and introduction.
- Short description.
- Key capabilities.
- Feature overview.
- Intended users.
- Project status.
- Documentation index linking to the other project documents.
- Development status and contribution guidance, where appropriate.
- Licensing placeholder if no licence has been selected.

Do not claim that features have already been implemented.

Clearly distinguish planned capabilities from completed functionality.

### C. architecture.md — Technical architecture

Propose a scalable and maintainable architecture suitable for the described application.

Include:

- Architectural goals.
- Major subsystems.
- Component responsibilities.
- Application structure.
- Data flow.
- State management.
- Storage and persistence.
- External integrations.
- API boundaries, if applicable.
- Security and privacy considerations.
- Error handling.
- Extensibility.
- Performance considerations.
- Deployment considerations.
- Suggested directory structure.
- Dependencies and technology considerations.

Technology decisions:

- Do not assume a programming language or framework unless specified.
- Prefer technology-independent architecture where possible.
- Where a technology decision is necessary, explain the alternatives and rationale.
- Distinguish mandatory requirements from recommendations.
- Avoid unnecessary microservices and infrastructure complexity.
- Consider offline-first or local execution where relevant to the concept.
- Design for future extensibility without overengineering the initial release.

Do not turn architecture.md into an implementation prompt or generate application code.

### D. roadmap.md — Development roadmap

Divide development into meaningful phases.

For each phase, describe:

- Objectives.
- Features included.
- Technical work.
- Dependencies.
- Expected deliverables.
- Completion criteria.

Use a sensible progression:

1. Project foundation.
2. Minimum viable product.
3. Core functionality.
4. Extended functionality.
5. Refinement and optimisation.
6. Future possibilities.

Adapt these phases to the actual project. Do not force unnecessary stages.

Distinguish between:
- Essential MVP requirements.
- Features that can follow the initial release.
- Optional future enhancements.

Do not assign artificial dates, budgets or completion percentages unless explicitly provided.

## 4. Feature interpretation rules

- Read all of `features.md`.
- Preserve the intent of every specified feature.
- Group related features logically.
- Identify dependencies between features.
- Distinguish functional requirements from non-functional requirements.
- Identify potential conflicts, ambiguities and missing information.
- Do not silently discard features.
- Do not invent major features and present them as user requirements.
- Additional recommendations must be clearly marked as suggestions.
- If features.md specifies a particular technology or implementation constraint, respect it unless there is a genuine conflict.

## 5. Consistency requirements

The four documents must agree with one another.

- `idea.md` defines the product.
- `README.md` introduces the product and links to its documentation.
- `architecture.md` explains how the product can be structured.
- `roadmap.md` explains how it can be developed.

Feature names, terminology and scope should remain consistent.

Do not duplicate entire sections unnecessarily. Cross-reference the other documents where appropriate.

## 6. Uncertainty and clarification

Before generating documentation, identify ambiguities that could materially change the product definition or architecture.

If critical information is missing, ask me specific clarification questions before creating the files.

Examples include:

- Unclear product purpose.
- Conflicting requirements.
- Unclear distinction between local and cloud operation.
- Important unspecified user workflows.
- Conflicting technology constraints.
- Ambiguous feature behaviour.

Do not ask questions about minor implementation choices that can reasonably be documented as assumptions.

When proceeding with assumptions, explicitly identify them in the appropriate document.

## 7. Execution rules

- Work inside the specified target folder only.
- Inspect existing files before creating anything.
- Read `features.md` completely.
- Preserve `features.md` unchanged.
- Preserve unrelated existing files.
- Do not generate source code.
- Do not generate build scripts or application scaffolding.
- Do not create additional documentation files unless requested.
- Create or update only the four required documents.
- If any of the four documents already exists, inspect it and update it carefully rather than blindly overwriting useful information.

## 8. Final verification

Before finishing:

- Verify that every feature in `features.md` has been accounted for.
- Verify that the architecture supports the defined product.
- Verify that the roadmap covers the MVP and subsequent development.
- Verify that the README links are correct.
- Check consistency across all four documents.
- Check that no planned feature is incorrectly described as implemented.

## Final output

Report:

- Documents created or updated.
- Summary of the product definition.
- Important architectural decisions.
- MVP scope.
- Major assumptions.
- Outstanding questions or unresolved conflicts.

The result should be a coherent project documentation package that another AI coding agent can use as the foundation for actual software development.
