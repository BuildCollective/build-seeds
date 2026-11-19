# SignalForge — Development Roadmap

**Project:** SignalForge  
**Roadmap Version:** 0.1  
**Initial Deployment:** GitHub Pages + GitHub Actions  
**Status:** Proposed

---

## Development Philosophy

SignalForge should be developed as a sequence of independently testable phases.

The first objective is not to build a complete publishing platform with every planned feature.

The first objective is to establish a reliable information-processing pipeline.

Each phase should produce a usable and verifiable result.

Development should prioritize:

1. Data integrity.
2. Source independence.
3. Intermediate processing.
4. Reliable deduplication.
5. AI synthesis.
6. Publishing.
7. Automation.
8. Presentation and administration.

Avoid implementing advanced features before the core pipeline is stable.

---

## Phase 0 — Project Foundation

**Objective:** Establish the project structure, development environment and configuration conventions.

### Tasks

- [ ] Establish project directory structure.
- [ ] Define core module boundaries.
- [ ] Define configuration format.
- [ ] Define installation identity.
- [ ] Define normalized record schema.
- [ ] Define source connector interface.
- [ ] Define intermediate handler interface.
- [ ] Define AI provider interface.
- [ ] Define publishing interface.
- [ ] Establish logging conventions.
- [ ] Establish testing framework.
- [ ] Establish GitHub Actions workflow structure.
- [ ] Establish documentation conventions.
- [ ] Add sample installation configuration.
- [ ] Add sample content profile.

### Completion criteria

- Project structure is established.
- Configuration can be loaded and validated.
- Core interfaces are documented.
- Sample records can be represented in the normalized schema.
- Basic automated tests execute successfully.

---

## Phase 1 — Source Collection

**Objective:** Collect information from initial source types.

### Tasks

- [ ] Implement RSS connector.
- [ ] Implement Atom connector.
- [ ] Implement JSON API connector.
- [ ] Implement basic HTML extraction connector.
- [ ] Implement source configuration.
- [ ] Implement source enable/disable controls.
- [ ] Implement source-specific request settings.
- [ ] Implement collection timestamps.
- [ ] Implement source execution logs.
- [ ] Implement basic retry handling.
- [ ] Implement source-level error isolation.

### Completion criteria

- Multiple sources can be collected in one execution.
- Source failures do not interrupt unrelated sources.
- Fetched records retain their source identity.
- Collection history is recorded.
- New records can be distinguished from previously collected records.

---

## Phase 2 — Intermediate Handler Engine

**Objective:** Establish the mandatory processing layer between source connectors and AI.

This is one of the most important phases.

### Tasks

- [ ] Implement raw record preservation.
- [ ] Implement common intermediate record representation.
- [ ] Implement handler registration.
- [ ] Implement sequential handler execution.
- [ ] Implement conditional handler execution.
- [ ] Implement handler-level configuration.
- [ ] Implement handler execution history.
- [ ] Implement parsing handlers.
- [ ] Implement metadata normalization.
- [ ] Implement content normalization.
- [ ] Implement validation handlers.
- [ ] Implement filtering handlers.
- [ ] Implement basic enrichment handlers.
- [ ] Implement record fingerprinting.
- [ ] Implement failed-handler recovery.
- [ ] Implement intermediate record inspection.

### Completion criteria

- All source records pass through the handler engine.
- Different source formats produce standardized records.
- Invalid records are prevented from entering downstream processing.
- Original source records remain preserved.
- New handlers can be added without modifying source connectors.
- No source connector invokes AI directly.

---

## Phase 3 — Deduplication and Classification

**Objective:** Identify duplicate records and classify information.

### Tasks

- [ ] Implement canonical URL matching.
- [ ] Implement source identifier matching.
- [ ] Implement content fingerprint matching.
- [ ] Implement exact duplicate detection.
- [ ] Implement near-duplicate candidate identification.
- [ ] Implement content profile loading.
- [ ] Implement category classification.
- [ ] Implement entity extraction.
- [ ] Implement domain-specific metadata handling.
- [ ] Implement classification status tracking.

### Completion criteria

- Exact duplicates are identified reliably.
- Records are not unnecessarily reprocessed.
- Different but related records remain distinguishable.
- Content profiles can define domain-specific fields.
- Classification results are stored separately from raw records.

---

## Phase 4 — AI Provider Integration

**Objective:** Integrate the first AI provider and establish structured AI processing.

### Tasks

- [ ] Implement Gemini provider adapter.
- [ ] Load credentials through GitHub Secrets.
- [ ] Implement provider configuration.
- [ ] Implement model configuration.
- [ ] Implement task-specific instructions.
- [ ] Implement structured response handling.
- [ ] Implement response validation.
- [ ] Implement timeout handling.
- [ ] Implement retry handling.
- [ ] Implement usage tracking where available.
- [ ] Implement AI processing logs.
- [ ] Implement configurable AI input limits.

### Initial AI tasks

- [ ] Record classification.
- [ ] Entity extraction.
- [ ] Duplicate evaluation.
- [ ] Related-record evaluation.

### Completion criteria

- AI requests receive validated intermediate records.
- API credentials never enter public output.
- Invalid AI responses are rejected.
- Provider failures do not corrupt processing state.
- AI operations can be tested independently.

---

## Phase 5 — Clustering and Intelligence Synthesis

**Objective:** Convert related records into consolidated intelligence.

### Tasks

- [ ] Implement cluster data model.
- [ ] Implement cluster creation.
- [ ] Implement candidate cluster identification.
- [ ] Implement record-to-cluster association.
- [ ] Implement cluster updates.
- [ ] Implement cluster merging.
- [ ] Implement cluster splitting.
- [ ] Implement synthesis input preparation.
- [ ] Implement article generation.
- [ ] Implement source attribution.
- [ ] Implement conflicting information identification.
- [ ] Implement content validation.
- [ ] Implement article version history.
- [ ] Implement cluster evolution.
- [ ] Implement update detection.

### Completion criteria

- Multiple records can produce one consolidated article.
- Every article retains traceable source references.
- New information can update an existing cluster.
- Previous article versions remain recoverable.
- Similarity does not automatically imply duplication.
- The system avoids unnecessary duplicate publishing.

---

## Phase 6 — Publishing Engine

**Objective:** Generate public website data from approved intelligence records.

### Tasks

- [ ] Implement article JSON generation.
- [ ] Implement article indexes.
- [ ] Implement category indexes.
- [ ] Implement tag indexes.
- [ ] Implement related article references.
- [ ] Implement search data generation.
- [ ] Implement RSS generation.
- [ ] Implement sitemap generation.
- [ ] Implement public output validation.
- [ ] Implement incremental publishing.
- [ ] Ensure internal data is excluded from public output.

### Completion criteria

- Approved articles can be published as structured JSON.
- RSS feeds are generated correctly.
- Search and category indexes are available.
- Source attribution is preserved.
- Private processing information is not published.

---

## Phase 7 — Static Frontend

**Objective:** Build the public website using GitHub Pages.

### Tasks

- [ ] Implement homepage.
- [ ] Implement article listing.
- [ ] Implement article detail pages.
- [ ] Implement category pages.
- [ ] Implement tag pages.
- [ ] Implement search.
- [ ] Implement filtering.
- [ ] Implement related articles.
- [ ] Implement source references.
- [ ] Implement pagination.
- [ ] Implement responsive layouts.
- [ ] Implement SEO metadata.
- [ ] Implement RSS discovery.
- [ ] Implement configurable branding.
- [ ] Implement basic native theme support.

### Completion criteria

- The frontend consumes generated public data.
- No backend server is required for normal browsing.
- Article pages and indexes are navigable.
- The site works under a GitHub Pages project URL.
- Frontend code contains no private credentials.

---

## Phase 8 — GitHub Actions Automation

**Objective:** Automate collection, processing and deployment.

### Tasks

- [ ] Implement scheduled collection workflow.
- [ ] Set hourly execution as the default.
- [ ] Implement manual workflow dispatch.
- [ ] Implement workflow input parameters.
- [ ] Implement configuration validation.
- [ ] Implement repository checkout and state restoration.
- [ ] Implement processing execution.
- [ ] Implement concurrency protection.
- [ ] Implement persistent state updates.
- [ ] Implement generated output commits where required.
- [ ] Implement GitHub Pages deployment.
- [ ] Implement workflow failure reporting.
- [ ] Implement partial failure reporting.
- [ ] Restrict workflow permissions.

### Completion criteria

- Scheduled execution collects new information.
- Manual execution works.
- Processing state persists between workflow runs.
- Concurrent runs cannot corrupt shared state.
- Generated public data is deployed automatically.
- API keys remain protected.

---

## Phase 9 — Configuration and Installation Experience

**Objective:** Make the platform reusable for independent websites.

### Tasks

- [ ] Finalize installation configuration schema.
- [ ] Implement sample installation template.
- [ ] Implement source configuration documentation.
- [ ] Implement content profile documentation.
- [ ] Implement AI instruction configuration.
- [ ] Implement handler configuration.
- [ ] Implement theme configuration.
- [ ] Implement installation validation.
- [ ] Implement repository template workflow.
- [ ] Implement platform version pinning.
- [ ] Document GitHub Secrets configuration.
- [ ] Document Pages deployment setup.
- [ ] Document custom domain configuration.

### Completion criteria

- A new installation can be created from the template.
- A new website can be configured without modifying core processing code.
- Its data, secrets and configuration remain independent.
- It can publish through its own GitHub Pages site.

---

## Phase 10 — Advanced Integrations and Improvements

**Objective:** Expand source compatibility and improve processing quality.

### Tasks

- [ ] Add additional scientific publication integrations.
- [ ] Add document extraction handlers.
- [ ] Add PDF extraction.
- [ ] Add full-text extraction.
- [ ] Add domain-specific metadata handlers.
- [ ] Add additional AI providers.
- [ ] Improve entity resolution.
- [ ] Improve cluster quality.
- [ ] Improve content update detection.
- [ ] Improve source reliability tracking.
- [ ] Improve data retention.
- [ ] Improve incremental processing.
- [ ] Improve search indexing.
- [ ] Improve theme customization.
- [ ] Add export and backup utilities.

### Completion criteria

- Additional source integrations use the existing connector and handler architecture.
- No new integration requires a separate AI-processing pipeline.
- Processing quality improves without compromising source attribution or data integrity.

---

## Phase 11 — Advanced Publishing Features

**Objective:** Expand the public website and management experience.

### Tasks

- [ ] Advanced native theme system.
- [ ] Theme ZIP import and export.
- [ ] Theme preview.
- [ ] Advanced article layouts.
- [ ] Advanced search and filtering.
- [ ] Topic timelines.
- [ ] Entity pages.
- [ ] Organization pages.
- [ ] Advanced archives.
- [ ] More publishing formats.
- [ ] WordPress Block Theme compatibility research.

These features should only be developed when the core platform is stable.

---

## Milestone Summary

| Milestone | Expected result |
|---|---|
| M0 | Project foundation |
| M1 | Source collection |
| M2 | Intermediate handler engine |
| M3 | Deduplication and classification |
| M4 | AI integration |
| M5 | Clustering and synthesis |
| M6 | Publishing engine |
| M7 | Public frontend |
| M8 | Automated deployment |
| M9 | Reusable installation |
| M10 | Advanced integrations |
| M11 | Advanced publishing |

---

## Development Rules

1. Complete and test one phase before moving to the next.
2. Avoid implementing future-phase functionality prematurely.
3. Maintain a working project after every milestone.
4. Keep source connectors independent of processing handlers.
5. Never bypass intermediate handlers.
6. Never expose API keys in public files.
7. Preserve raw records and source attribution.
8. Maintain automated tests for processing modules.
9. Keep configuration separate from application logic.
10. Document significant architectural decisions.
11. Avoid unnecessary dependencies.
12. Prefer incremental processing over complete rebuilds.
13. Keep generated public data separate from internal processing state.
14. Do not introduce microservices without a demonstrated requirement.

## Initial Definition of Done

The first meaningful release is complete when SignalForge can:

1. Collect records from multiple RSS, Atom and JSON sources.
2. Preserve original source information.
3. Convert collected records into a standardized representation.
4. Process all records through intermediate handlers.
5. Validate and normalize records.
6. Detect duplicates.
7. Identify related records.
8. Use Gemini to synthesize consolidated content.
9. Preserve source attribution.
10. Update existing intelligence records when new information arrives.
11. Generate JSON and RSS outputs.
12. Publish the resulting website through GitHub Pages.
13. Execute automatically through GitHub Actions.

**The first release should prove the intelligence pipeline, not the completeness of the administration interface.**
