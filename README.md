# Universal Information Standard (UIS)

**UIS defines the canonical structure for representing extracted information.**

## The Scope Boundary

```
┌─────────────────────────────────────────────────────────────┐
│                        OUTSIDE UIS                            │
│                    Extraction / Ingestion                     │
│            (PDF parsing, OCR, AI, human review, etc.)        │
└─────────────────────────────────────────────────────────────┘
                              │
                              ▼
═══════════════════════════════════════════════════════════════
                        UIS STARTS HERE
═══════════════════════════════════════════════════════════════
     ┌─────────────────────────────────────────────────┐
     │        Canonical Information Record              │
     │        (What UIS actually standardizes)          │
     └─────────────────────────────────────────────────┘
═══════════════════════════════════════════════════════════════
                         UIS ENDS HERE
═══════════════════════════════════════════════════════════════
                              │
                              ▼
┌─────────────────────────────────────────────────────────────┐
│                         OUTSIDE UIS                          │
│              Storage / Search / Analytics / AI              │
│                    (Databases, search engines, apps)        │
└─────────────────────────────────────────────────────────────┘
```

UIS is NOT an ingestion framework, ETL pipeline, OCR system, database, or application. UIS's sole purpose is to define the structure of information records—after extraction has already occurred.

## What UIS Standardizes

UIS defines the **structure** of information records:

| Element | Purpose |
|---------|---------|
| Identity | How records are uniquely identified |
| Classification | How records are categorized |
| Content | The extracted information |
| Relationships | How records connect to each other |
| Provenance | Reference to source artifact |

UIS does **NOT** standardize:
- How information is extracted (parsing, OCR, AI, human review)
- How information is stored (databases, files, cloud storage)
- How information is consumed (search, analytics, AI reasoning)
- File formats, APIs, programming languages, or business rules

## Why This Scope?

Once information has been extracted, systems need to share it. Without a common structure:

- Each system invents its own representation
- Cross-system integration requires custom adapters
- Information semantics vary between implementations

UIS provides a universal representation that any extractor can produce and any consumer can understand.

## Current Status

**Stage**: Early research and design

**Focus**: Defining the minimal canonical record structure

**Key question**: What elements are universal across all domains?

See [docs/PROJECT-STATUS.md](docs/PROJECT-STATUS.md) for details.

## Documentation

| Document | Purpose |
|----------|---------|
| [docs/001-scope.md](docs/001-scope.md) | What UIS covers and excludes |
| [docs/003-terms-and-definitions.md](docs/003-terms-and-definitions.md) | Key terminology |
| [docs/004-design-principles.md](docs/004-design-principles.md) | Core principles |
| [docs/DISCUSSION-0001-information.md](docs/DISCUSSION-0001-information.md) | Research: what is information? |
| [docs/DISCUSSION-0002-scope-of-uis.md](docs/DISCUSSION-0002-scope-of-uis.md) | Research: what should UIS scope? |
| [docs/DISCUSSION-0003-canonical-information-model.md](docs/DISCUSSION-0003-canonical-information-model.md) | Research: can one model work? |
| [docs/DISCUSSION-0004-boundaries.md](docs/DISCUSSION-0004-boundaries.md) | Research: what is outside scope? |
| [docs/PROJECT-STATUS.md](docs/PROJECT-STATUS.md) | Current state and milestones |

## Participation

This is an early-stage research project exploring a specific question: what is the minimal canonical structure for representing extracted information?

To contribute:
- Review the research documents
- Share feedback on the scope
- Suggest domain examples

See [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines.

## License

Apache License 2.0 — see [LICENSE](LICENSE)
