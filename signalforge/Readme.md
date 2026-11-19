# SignalForge

**An AI-powered information aggregation, synthesis and intelligence publishing platform.**

SignalForge collects information from multiple sources, processes it into standardized records, identifies duplicates and relationships, synthesizes relevant information using AI, and publishes consolidated intelligence through independent websites.

The platform is designed to power multiple information domains using a common processing engine.

---

## What is SignalForge?

Information is scattered across websites, APIs, publications, databases and other sources.

SignalForge aims to make this information easier to follow by automatically collecting, organizing, connecting and synthesizing it.

Rather than simply displaying a collection of links, the platform identifies related information and creates consolidated records with traceable source attribution.

When new information becomes available, existing records can evolve instead of generating unnecessary duplicate articles.

## Example Applications

| Website type | Information |
|---|---|
| Technology Intelligence | Products, companies, software and releases |
| Research Intelligence | Scientific papers and research developments |
| Job Intelligence | Employment opportunities and vacancies |
| Startup Intelligence | Startups, investments and funding |
| Patent Intelligence | Patents and innovation |
| Cybersecurity Intelligence | Vulnerabilities, incidents and security developments |
| Policy Intelligence | Regulations, government notifications and policies |
| Clinical Intelligence | Medical and clinical research |

Each website can operate independently with its own branding, sources, AI instructions, content profile and publishing configuration.

## How It Works

SignalForge follows a structured processing pipeline.

```text
Information Sources
        |
        v
Source Connectors
        |
        v
Intermediate Handlers
        |
        v
Normalized Records
        |
        v
Validation and Enrichment
        |
        v
Deduplication
        |
        v
Classification and Clustering
        |
        v
AI Synthesis
        |
        v
Content Validation
        |
        v
Publishing
        |
        v
GitHub Pages Website
```

### Why intermediate handlers?

Different information sources provide different formats and metadata.

An RSS feed, a scientific publication API and a job portal cannot be assumed to provide equivalent information.

Every source must therefore pass through intermediate processing handlers.

These handlers normalize and validate the information before it becomes eligible for AI processing.

Raw fetched responses must never be sent directly to an AI provider.

This makes it possible to add future non-RSS integrations without redesigning the central intelligence engine.

## Initial Deployment

SignalForge initially uses GitHub as its execution and publishing environment.

| Component | Responsibility |
|---|---|
| GitHub Pages | Public website |
| GitHub Actions | Scheduled collection and processing |
| GitHub repository | Configuration and versioned processing data |
| GitHub Secrets | Private API credentials |
| JSON | Structured content for the frontend |
| RSS | Generated public feeds |
| AI provider | Classification, evaluation and synthesis |

The default collection frequency is hourly.

Manual workflow execution should also be available.

The initial version is designed around public, read-only websites. Browser-based administration, user accounts and personalized services are not required for the first implementation.

## Main Features

- Multiple independent website installations.
- Configurable information sources.
- RSS, Atom and JSON integrations.
- Basic HTML extraction.
- Extensible source connector architecture.
- Intermediate data processing handlers.
- Metadata normalization and enrichment.
- Record validation.
- Duplicate detection.
- Related-record clustering.
- Configurable content profiles.
- Multiple AI provider support.
- AI-powered content synthesis.
- Source attribution.
- Evolving intelligence records.
- Article version history.
- Automatic publishing.
- Generated JSON feeds.
- Generated RSS feeds.
- Configurable website branding.
- Native themes.
- Public search and filtering.
- Scheduled GitHub Actions processing.

## Repository Structure

The intended implementation may follow a structure similar to:

```text
signalforge/
│
├── frontend/
│   ├── src/
│   ├── assets/
│   └── themes/
│
├── engine/
│   ├── connectors/
│   ├── handlers/
│   ├── normalization/
│   ├── validation/
│   ├── deduplication/
│   ├── classification/
│   ├── clustering/
│   ├── synthesis/
│   └── publishing/
│
├── profiles/
│
├── config/
│
├── data/
│   ├── raw/
│   ├── normalized/
│   ├── clusters/
│   └── history/
│
├── public/
│   ├── data/
│   ├── articles/
│   └── feeds/
│
├── scripts/
│
├── .github/
│   └── workflows/
│
├── docs/
│
├── features.md
├── idea.md
├── architecture.md
├── roadmap.md
└── README.md
```

This is an indicative organization, not a finalized implementation requirement. The architecture document defines the intended responsibilities of these components.

## Project Documentation

| Document | Purpose |
|---|---|
| `idea.md` | Product concept, objectives and long-term vision |
| `features.md` | Categorized feature inventory |
| `architecture.md` | Technical architecture and processing design |
| `roadmap.md` | Development phases and implementation priorities |
| `README.md` | Project overview and usage direction |

## Initial Development Scope

The first implementation should establish a working intelligence publishing pipeline.

Priorities:

1. Source collection.
2. Intermediate record representation.
3. Processing handlers.
4. Normalization and validation.
5. Duplicate detection.
6. Gemini integration.
7. Classification and clustering.
8. AI synthesis.
9. Source attribution.
10. JSON and RSS generation.
11. GitHub Pages deployment.
12. Scheduled GitHub Actions execution.

Advanced administration, accounts, subscriptions, theme compatibility extensions and additional source integrations can follow after the core pipeline is validated.

## Design Principles

1. Domain-independent architecture.
2. Source connectors separated from processing handlers.
3. No direct raw-source-to-AI processing.
4. Structured intermediate records.
5. Preservation of original source information.
6. Traceable source attribution.
7. Replaceable AI providers.
8. Configurable content profiles.
9. Versioned synthesized content.
10. Independent website installations.
11. Reusable processing components.
12. Minimal infrastructure for the initial implementation.

## Current Status

**Concept stage.**

The objective is to finalize the architecture and implementation requirements before beginning development.

SignalForge should first prove that a single reusable pipeline can collect, process, synthesize and publish information reliably.

**The goal is not to build another news aggregator. It is to build an engine for creating specialized intelligence websites.**
