# BuildSeeds

**A structured library of software ideas and documentation seeds.**

BuildSeeds captures software concepts and turns them into coherent documentation that can guide later design and implementation. It is intentionally idea-first: a concept is not automatically a coding task, and a technology stack is not imposed without a reason.

## What belongs here?

Each concept should have its own folder. The primary input is `features.md`, containing the features and requirements supplied by the idea's author.

A completed concept folder contains:

- `features.md` — original user-provided feature list; preserve it unchanged.
- `idea.md` — purpose, problem, audience, goals, scope and product concept.
- `README.md` — concise project overview and usage context.
- `architecture.md` — proposed system structure, components, data flow and technical considerations.
- `roadmap.md` — staged development plan, including MVP and later possibilities.

## Suggested structure

```text
build-seeds/
├── README.md
├── index.html
└── <concept-name>/
    ├── features.md
    ├── idea.md
    ├── README.md
    ├── architecture.md
    └── roadmap.md
```

## Documentation principles

1. Read the complete `features.md` before drafting.
2. Preserve `features.md` exactly; do not rewrite the source input.
3. Inspect existing documentation before creating or updating files.
4. Ask questions when a critical ambiguity would change the product or architecture.
5. Do not invent requirements or present assumptions as confirmed decisions.
6. Separate MVP requirements from optional or future enhancements.
7. Keep all documents consistent with one another.
8. Do not generate application source code as part of the documentation process.

## Technology choices

BuildSeeds does not mandate a programming language, framework, database or deployment model. Architecture recommendations should follow from the concept's actual needs. Where a decision is uncertain, record the options and trade-offs rather than pretending it has been decided.

## Relationship to BuildCollective

- **BuildSeeds** defines what could be built and why.
- **Visual DNA** describes how an interface could look and feel.
- **InterfaceFoundry** provides working interface references.

A seed can be used on its own or combined with resources from the other repositories.

## Contributing

Submit concepts with clear scope and useful feature descriptions. Identify assumptions, constraints and unresolved questions. Avoid embedding credentials, private data or material you do not have permission to share.

## Licence

This project is intended for public-domain-style reuse under **CC0 1.0 Universal**, subject to the repository licence and any separate third-party notices.
