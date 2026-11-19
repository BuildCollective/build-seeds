# SignalForge — Feature Specification

**Project:** SignalForge  
**Category:** AI / Information Aggregation / Intelligence Publishing  
**Status:** Concept / Proposed  
**Repository:** BuildCollective / BuildSeeds

---

## 1. Multi-Installation Management

Features for creating and managing independent websites using the same platform.

- Independent website installations.
- Unique website identity for each installation.
- Independent configurations and content databases.
- Independent source lists and collection schedules.
- Independent AI provider configurations.
- Independent AI instructions and content profiles.
- Independent themes and branding.
- Independent publishing rules.
- Independent data retention policies.
- Independent deployment configurations.
- Ability to upgrade the shared platform without overwriting installation-specific settings.

Each installation should operate independently without requiring changes to the central platform.

## 2. Website Identity and Configuration

Features for configuring the identity and behaviour of an individual website.

- Website name.
- Website description.
- Logo and favicon.
- Banner and featured branding assets.
- Custom domain configuration.
- Website language and regional settings.
- Time zone configuration.
- Default date and time formats.
- Navigation configuration.
- Footer configuration.
- Social links.
- Metadata and SEO settings.
- Default article layout.
- Default content profile.
- Default publishing behaviour.
- Website visibility and indexing preferences.

Configuration should be manageable independently for every installation.

## 3. Information Source Management

Features for registering and managing information sources.

### 3.1 Initial source integrations

- RSS feeds.
- Atom feeds.
- JSON APIs.
- Public website HTML extraction.
- XML-based structured sources.

### 3.2 Source configuration

- Source name and description.
- Source URL or endpoint.
- Source type.
- Source category.
- Source priority or reliability level.
- Collection frequency.
- Enable/disable controls.
- Custom request headers.
- Authentication configuration where supported.
- Source-specific extraction rules.
- Maximum records per collection run.
- Source-specific processing instructions where necessary.

### 3.3 Source monitoring

- Last collection attempt.
- Last successful collection.
- Number of fetched records.
- Number of new records.
- Number of records rejected during processing.
- Number of records forwarded to downstream processing.
- Collection duration.
- Error history.
- Source availability.
- Automatic retry for temporary failures.

### 3.4 Future source integrations

The connector system should be extensible beyond conventional RSS and JSON sources.

Potential future integrations include:

- Research publication databases.
- Scientific literature APIs.
- PubMed and Europe PMC.
- Crossref and OpenAlex.
- Patent databases.
- Job portals and career websites.
- Government announcement portals.
- Regulatory and policy databases.
- Funding and grant databases.
- Product and software release APIs.
- GitHub repositories and release feeds.
- Public discussion platforms.
- News APIs.
- Publicly accessible structured datasets.
- Other domain-specific APIs and data providers.

Future connectors should be added through dedicated integration modules rather than modifying the central processing pipeline.

All integrations must respect applicable API terms, access permissions, rate limits and website policies.

## 4. Intermediate Data Processing and Handler System

<badge color="success">Core requirement</badge>

A mandatory intermediate processing layer must exist between source collection and AI processing.

**Fetched information must never be passed directly from a source connector to an AI provider.**

Every source integration must feed into a standardized processing pipeline.

This requirement is particularly important for future non-RSS integrations, where different platforms may provide completely different data structures, metadata and content formats.

### 4.1 Connector output handling

- Receive information from individual source connectors.
- Preserve original fetched responses or relevant source records.
- Identify the source and connector responsible for each record.
- Validate incoming data.
- Handle incomplete or malformed records.
- Convert source-specific responses into an intermediate representation.

### 4.2 Normalization handlers

- Normalize titles and descriptions.
- Standardize publication dates and timestamps.
- Normalize URLs.
- Extract author and publisher information.
- Standardize source metadata.
- Identify content type.
- Extract available entities.
- Normalize categories and tags.
- Standardize structured fields.
- Handle missing metadata.
- Remove irrelevant formatting and boilerplate where appropriate.

### 4.3 Enrichment handlers

- Extract additional metadata.
- Resolve source identifiers.
- Identify DOI, PMID, job IDs and other domain-specific identifiers.
- Extract entities such as organizations, products, people and locations.
- Retrieve additional permitted metadata where necessary.
- Associate records with known entities.
- Identify relevant domain-specific attributes.

### 4.4 Validation handlers

- Check record completeness.
- Validate required fields.
- Detect malformed or unusable records.
- Identify invalid URLs.
- Detect unsupported content types.
- Identify records with insufficient information.
- Flag records requiring manual inspection.

### 4.5 Filtering handlers

- Filter irrelevant records.
- Apply source-specific inclusion rules.
- Apply domain-specific criteria.
- Remove unwanted categories.
- Filter records based on configurable keywords or metadata.
- Apply date and relevance constraints.

### 4.6 Deduplication handlers

- Exact URL matching.
- Identifier-based matching.
- Content fingerprinting.
- Title and metadata similarity.
- Near-duplicate detection.
- Source-aware duplicate evaluation.
- Domain-specific duplicate rules.

### 4.7 Intermediate record management

- Store normalized records independently of original source responses.
- Maintain references to original records.
- Preserve processing status.
- Track handler execution history.
- Support reprocessing when handler logic changes.
- Allow failed records to be retried.
- Support inspection of intermediate records.
- Avoid unnecessary repeated AI processing.

### 4.8 Extensible handler registry

The platform should support additional processing handlers without requiring modifications to every source connector.

Examples of future handlers:

- PDF document extraction.
- Full-text article extraction.
- Scientific abstract extraction.
- Table extraction.
- Image metadata extraction.
- Transcript extraction.
- Document classification.
- Language detection.
- Translation.
- Domain-specific metadata extraction.

Handlers should be composable and configurable.

The processing pipeline must allow multiple handlers to operate sequentially or conditionally.

**AI processing should only receive validated, normalized and appropriately enriched intermediate records.**

---

## 5. Domain Profiles and Content Models

Features for adapting the same platform to different information domains.

### 5.1 Content profile configuration

Each profile should define:

- Record types.
- Required metadata.
- Optional metadata.
- Domain-specific identifiers.
- Entity types.
- Duplicate detection rules.
- Related-record matching rules.
- Classification categories.
- AI instructions.
- Synthesis requirements.
- Publishing fields.
- Content validation rules.

### 5.2 Supported example profiles

**Technology intelligence**

- Companies.
- Products.
- Software.
- Releases and versions.
- Technology categories.
- Announcements.
- Product launches.
- Security updates.

**Scientific research intelligence**

- Publications.
- DOI and PMID.
- Authors.
- Institutions.
- Journals.
- Publication dates.
- Organisms and biological subjects.
- Experimental methodologies.
- Research findings.
- Study types.

Scientific research profiles must preserve differences between methodologies, experiments and findings. Similarity between papers must not automatically imply identical conclusions.

**Job intelligence**

- Employers.
- Job titles.
- Job identifiers.
- Locations.
- Experience requirements.
- Salary information.
- Employment types.
- Application URLs.
- Posting and closing dates.

Job matching must consider actual vacancy identifiers and requirements rather than title similarity alone.

**Startup and funding intelligence**

- Organizations.
- Founders.
- Investors.
- Funding rounds.
- Investment amounts.
- Acquisition announcements.
- Funding dates.
- Industry categories.

**Policy and regulatory intelligence**

- Government departments.
- Regulations.
- Notifications.
- Legislation.
- Policy documents.
- Effective dates.
- Jurisdictions.
- Amendments.

Additional profiles should be configurable without modifying the central processing engine.

---

## 6. AI Provider Management

Features for configuring AI providers and models.

### 6.1 Provider integrations

- Google Gemini.
- OpenAI.
- Anthropic Claude.
- OpenAI-compatible APIs.
- Local AI endpoints in supported deployment environments.
- Additional providers through an extensible integration interface.

### 6.2 Provider configuration

- Provider selection.
- API endpoint.
- Model selection.
- API key configuration.
- Generation parameters.
- Token limits.
- Request timeout.
- Retry configuration.
- Usage limits.
- Cost tracking where supported.
- Provider availability testing.

### 6.3 AI task configuration

Separate instructions should be configurable for individual AI operations.

- Classification.
- Entity extraction.
- Metadata extraction.
- Duplicate evaluation.
- Related-record evaluation.
- Cluster assignment.
- Content synthesis.
- Article updates.
- Summary generation.
- Tag generation.
- Content quality evaluation.

### 6.4 AI processing controls

- Select AI provider per task.
- Select model per task.
- Configure prompts per content profile.
- Configure output formats.
- Validate structured AI responses.
- Retry invalid responses.
- Limit unnecessary AI calls.
- Track AI processing history.
- Track token consumption where available.
- Configure spending limits where supported.

API keys must never be exposed to the public frontend.

---

## 7. Intelligence Clustering and Synthesis

Features for identifying relationships between information records and generating consolidated content.

### 7.1 Record classification

- Classify records into configured categories.
- Identify relevant entities.
- Identify the main subject.
- Identify record type.
- Assign domain-specific metadata.
- Determine processing eligibility.

### 7.2 Related-record identification

- Identify records describing the same event or development.
- Identify records concerning the same organization or entity.
- Identify records discussing related research.
- Identify records belonging to the same opportunity or announcement.
- Support configurable similarity thresholds.
- Support deterministic and AI-assisted matching.

### 7.3 Cluster management

- Create clusters.
- Associate records with existing clusters.
- Split incorrectly merged clusters.
- Merge duplicate clusters.
- Remove incorrect record associations.
- Track cluster history.
- Track cluster membership.
- Support manual corrections.
- Support automated cluster updates.

### 7.4 Content synthesis

- Generate consolidated titles.
- Generate summaries.
- Generate detailed articles.
- Combine relevant information from multiple sources.
- Preserve source attribution.
- Identify conflicting information.
- Identify missing information.
- Distinguish facts from interpretations.
- Avoid unsupported conclusions.
- Preserve important differences between sources.

### 7.5 Evolving intelligence records

- Add newly discovered sources to existing clusters.
- Update synthesized articles when relevant information changes.
- Preserve previous published versions.
- Track when new evidence was added.
- Track which sources contributed to each update.
- Avoid creating unnecessary duplicate articles.
- Support manual review of significant changes.

---

## 8. Content Management and Publishing

Features for managing synthesized content.

### 8.1 Article management

- Article title.
- Short summary.
- Detailed content.
- Featured image.
- Categories.
- Tags.
- Publication date.
- Last updated date.
- Related entities.
- Related articles.
- Original source references.
- Source attribution.
- Content status.

### 8.2 Publishing controls

- Automatic publishing.
- Draft generation.
- Manual approval.
- Scheduled publishing.
- Unpublishing.
- Article revision.
- Article deletion.
- Content correction.
- Re-publication after updates.

### 8.3 Article history

- Preserve published versions.
- Track modifications.
- Compare previous and current versions.
- Identify newly added source records.
- Maintain source-to-content relationships.
- Record processing timestamps.

### 8.4 Publishing outputs

- Public website pages.
- JSON data feeds.
- RSS feeds.
- Sitemap.
- Structured metadata.
- Search indexes.
- Category archives.

---

## 9. Public Website Features

Features available to website visitors.

- Homepage.
- Latest articles.
- Category pages.
- Topic pages.
- Article detail pages.
- Search.
- Keyword filtering.
- Date filtering.
- Category filtering.
- Tag filtering.
- Related articles.
- Source references.
- Pagination.
- Archives.
- Responsive layouts.
- SEO metadata.
- Sitemap generation.
- RSS subscription.
- Social sharing.
- Custom navigation.
- Configurable footer.

The public website should be usable without requiring visitor registration.

---

## 10. Theme and Appearance Management

Features for configuring website presentation.

### 10.1 Native theme support

- Multiple native themes.
- Theme selection.
- Theme activation and deactivation.
- Theme preview.
- Theme customization.
- Typography configuration.
- Color palettes.
- Layout configuration.
- Custom CSS.
- Custom assets.
- Responsive layout support.

### 10.2 Theme packages

- Import theme ZIP packages.
- Export themes.
- Validate uploaded themes.
- Preview before activation.
- Manage installed themes.
- Switch themes without modifying content data.
- Preserve installation-specific branding settings.

### 10.3 Future WordPress Block Theme compatibility

Potential support for:

- `theme.json`.
- Block templates.
- Template parts.
- Global styles.
- CSS and assets.
- Common WordPress blocks.
- Supported block patterns.

This compatibility layer should not require WordPress itself.

Classic PHP themes, arbitrary PHP execution, `functions.php` and WordPress plugin dependencies are outside the initial feature scope.

---

## 11. Administration and Setup

Features for managing individual installations.

### 11.1 First-run setup

- Detect uninitialized installations.
- Display setup interface.
- Configure website identity.
- Create administrator credentials where supported.
- Select content profile.
- Configure AI provider.
- Add information sources.
- Configure collection schedules.
- Select a theme.
- Initialize publishing configuration.
- Lock setup after successful initialization.

### 11.2 Administration dashboard

- Collection activity.
- Processing statistics.
- Source health.
- New records.
- Duplicate records.
- Active clusters.
- Published articles.
- Drafts awaiting approval.
- AI usage.
- Failed processing jobs.
- Recent system errors.

### 11.3 Management sections

- Sources.
- Intermediate records.
- Processing handlers.
- Processing history.
- Clusters.
- Articles.
- Content profiles.
- AI providers.
- AI prompts.
- Themes.
- Website settings.
- User management.
- System logs.
- Backups.

The availability of browser-based administration depends on the deployment profile.

---

## 12. User Accounts and Access Management

Optional features for installations that require user-specific functionality.

- User registration.
- Login and authentication.
- Password recovery.
- User profiles.
- User roles.
- Administrator permissions.
- Saved articles.
- Saved searches.
- Followed topics.
- Personalized feeds.
- RSS subscriptions.
- User-specific alerts.

A public read-only deployment must not require this functionality.

---

## 13. Notifications and Subscriptions

Future user-facing notification features.

- Email notifications.
- New article alerts.
- Topic alerts.
- Keyword alerts.
- Saved-search alerts.
- RSS feed subscriptions.
- Personalized notification preferences.
- Free and paid subscription tiers.
- Notification frequency configuration.
- Subscription management.

Payment processing and user-specific notifications require an appropriate server-side deployment or external service.

---

## 14. Data Management and Storage

Features for preserving information and processing history.

- Preserve original fetched records.
- Store normalized intermediate records.
- Store enriched records.
- Store entity metadata.
- Store clusters and cluster membership.
- Store synthesized content.
- Preserve article versions.
- Preserve source attribution.
- Maintain processing history.
- Support configurable retention.
- Support backups and restoration.
- Support data export.
- Support migration between storage backends.

Storage must be abstracted so repository-based storage can be replaced by database-backed storage without changing the intelligence processing rules.

---

## 15. Automation and Scheduling

- Configurable collection schedules.
- Hourly collection as the default initial schedule.
- Manual execution.
- Per-source scheduling.
- Separate collection and synthesis schedules.
- Scheduled publishing.
- Automatic retry.
- Failed-job recovery.
- Processing checkpoints.
- Batch processing.
- Duplicate-safe execution.
- Execution history.
- Configurable processing limits.

---

## 16. Security and Reliability

- Secure API key storage.
- Never expose secrets to frontend code.
- Restrict administrative operations.
- Validate uploaded files.
- Avoid arbitrary code execution from uploaded themes.
- Validate external URLs.
- Prevent server-side request forgery.
- Respect source API rate limits.
- Handle temporary source failures.
- Isolate source errors.
- Validate AI responses.
- Maintain processing logs.
- Restrict deployment workflow permissions.
- Protect private processing state.
- Ensure repeated execution does not generate duplicate content.
- Support recovery from interrupted processing.

---

## 17. Deployment Profiles

The platform should support multiple deployment approaches while retaining shared processing logic and data contracts.

### 17.1 Primary initial approach: GitHub Pages + GitHub Actions

Features:

- Static frontend hosted through GitHub Pages.
- Scheduled collection through GitHub Actions.
- Manual workflow execution.
- GitHub Secrets for AI credentials.
- Repository-based configuration.
- Generated JSON publishing.
- Generated RSS publishing.
- Version-controlled content and processing state.
- Independent repository for each installation.
- Configurable workflow frequency.

Initial limitations:

- No continuously available application server.
- No native dynamic API backend.
- No native user authentication.
- No private user-specific services.
- Limited suitability for large-scale persistent data storage.
- Scheduled jobs may be delayed.

The public website must contain only intentionally published data.

### 17.2 Alternative: Vercel + Node.js

Potential features:

- Dynamic server-side application.
- Browser-based administration.
- API routes.
- Authentication.
- Database integration.
- Server-side AI processing.
- Dynamic publishing.
- User-specific services.
- External object storage.

Potential technology choices:

- TypeScript.
- Node.js.
- Next.js or equivalent.
- PostgreSQL.
- Suitable background job or scheduled processing system.

### 17.3 Alternative: PHP + MySQL/MariaDB

Potential features:

- Conventional shared-hosting deployment.
- PHP-based application.
- MySQL/MariaDB storage.
- Browser-based administration.
- Database-backed processing queue.
- Cron-based collection.
- Server-side AI integrations.
- User accounts.
- Dynamic publishing.
- Subscription management.

The PHP deployment should be designed to work without requiring Node.js or Docker on conventional supported shared-hosting environments.

### 17.4 Deployment flexibility

- Shared processing contracts.
- Deployment-specific adapters.
- Storage abstraction.
- Provider abstraction.
- Configurable scheduling.
- Environment-specific secret management.
- Migration between supported storage backends.
- Independent deployment configuration.

Initial development should prioritize GitHub Pages and GitHub Actions. Alternative deployments should be introduced progressively rather than developed as parallel implementations from the beginning.

---

## 18. Extensibility and Future Integrations

- Plugin-style source connectors.
- Pluggable intermediate processing handlers.
- Additional AI providers.
- Additional content profiles.
- Custom entity extractors.
- Domain-specific validation.
- Additional publishing formats.
- External search integrations.
- External notification providers.
- Additional storage adapters.
- Theme extensions.
- Import and export integrations.

New integrations should connect through defined interfaces rather than bypassing the central processing pipeline.

In particular, new information sources must pass through the intermediate handler system before entering classification, clustering or AI synthesis.

---

## 19. Feature Prioritization

### Phase 1 — Core publishing engine

- GitHub Pages frontend.
- GitHub Actions automation.
- RSS and Atom collection.
- JSON source integration.
- Basic HTML extraction.
- Intermediate record representation.
- Normalization handlers.
- Validation handlers.
- Basic deduplication.
- Gemini integration.
- AI classification.
- Related-record clustering.
- AI synthesis.
- Source attribution.
- JSON publishing.
- RSS output.
- Basic categories and search.
- Processing logs.

### Phase 2 — Processing and content improvements

- Extensible handler registry.
- More sophisticated deduplication.
- Entity extraction.
- Cluster evolution.
- Article versioning.
- Additional AI providers.
- Configurable content profiles.
- Improved source monitoring.
- Native theme management.
- Content moderation.

### Phase 3 — Administration and integrations

- Browser-based administration.
- Additional non-RSS integrations.
- Advanced HTML and document extraction.
- Additional metadata enrichment.
- More sophisticated theme customization.
- Search improvements.
- Additional publishing formats.
- Better backup and restoration.

### Phase 4 — Server deployments

- Node.js deployment.
- Vercel compatibility.
- Database-backed storage.
- PHP/MySQL deployment.
- Conventional shared-hosting support.
- User accounts.
- Notifications.
- Subscription management.

### Phase 5 — Advanced ecosystem

- WordPress Block Theme compatibility.
- Theme ecosystem.
- Advanced domain-specific handlers.
- Additional AI providers and local models.
- External integrations.
- Advanced analytics.
- More sophisticated user personalization.

---

## 20. Essential Design Constraints

1. SignalForge must remain domain-independent.
2. Source connectors must remain separate from processing handlers.
3. Raw fetched data must never be passed directly to AI.
4. All records must pass through a standardized intermediate representation.
5. Intermediate handlers must be extensible and composable.
6. Original source records must remain traceable.
7. AI synthesis must preserve source attribution.
8. Related records must not automatically be treated as identical.
9. Existing intelligence clusters must support future updates.
10. Previous published content versions must remain recoverable.
11. Themes must remain separate from content and processing logic.
12. AI provider integrations must remain replaceable.
13. Storage must not be permanently coupled to GitHub repositories.
14. Deployment profiles must reuse shared processing contracts.
15. The initial implementation must avoid unnecessary infrastructure and excessive scope.

**Primary feature principle:** SignalForge should be capable of accepting information from increasingly diverse sources without requiring changes to its central intelligence engine. The intermediate handler system is the mechanism that makes this possible.
