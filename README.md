# Universal Information Standard (UIS)

**UIS maps information from any source into a canonical structure—without modifying the original.**

## The Problem

Information exists in countless formats:
- PDFs and documents
- Sensor readings (COMTRADE, PLC tags)
- Images (JPEG, DICOM)
- Database records
- Audio and video
- Email and messages

Each uses different structures. This fragmentation makes it hard to:
- Exchange information across domains
- Build systems that work with diverse types
- Maintain quality and traceability

## The Core Insight

> **UIS does not replace or transform original artifacts. UIS maps information from artifacts into a canonical information model.**

Original artifacts stay unchanged. UIS creates a universal representation that coexists with source data.

```
┌─────────────┐     ┌─────────┐     ┌────────────────────┐
│   Reality   │────▶│Artifacts│────▶│   Mapping Layer    │
└─────────────┘     └─────────┘     └─────────┬──────────┘
                                               │
                    ┌──────────────────────────▼──────────┐
                    │   Canonical Information Record       │
                    └──────────────────────────┬──────────┘
                                               │
                    ┌──────────────────────────▼──────────┐
                    │        Knowledge Systems            │
                    └─────────────────────────────────────┘
```

## What UIS Standardizes

UIS defines the **structure** of information records:

| Element | Purpose |
|---------|---------|
| Identity | How records are identified |
| Classification | How records are categorized |
| Content | The actual information |
| Relationships | How records connect |
| Provenance | Where information came from |

UIS does **NOT** standardize:
- File formats (PDF, JSON, XML)
- Databases
- APIs
- Programming languages
- Business rules

## Current Status

**Stage**: Early research and design

**What we've established**:
- The information mapping architecture concept
- A draft scope and terminology
- Foundational design principles
- The idea that original artifacts should be preserved

**What we don't know yet**:
- The exact structure of canonical records
- How to handle domain-specific semantics
- How quality and confidence should work
- The best approach to evidence and provenance

## Research Questions

We're exploring fundamental questions before writing a formal specification:

1. **What is information?** (docs/DISCUSSION-0001-information.md)
2. **What should UIS actually scope?** (docs/DISCUSSION-0002-scope-of-uis.md)
3. **Can one model represent everything?** (docs/DISCUSSION-0003-canonical-information-model.md)
4. **What are UIS boundaries?** (docs/DISCUSSION-0004-boundaries.md)

See [docs/PROJECT-STATUS.md](docs/PROJECT-STATUS.md) for details.

## Repository Structure

```
/
├── README.md              # This file
├── LICENSE                # Apache 2.0
├── CODE_OF_CONDUCT.md
├── CONTRIBUTING.md
└── docs/
    ├── 001-scope.md                  # What UIS covers
    ├── 003-terms-and-definitions.md # Key terminology
    ├── 004-design-principles.md      # Core principles
    ├── 005-architecture.md           # High-level architecture
    ├── DISCUSSION-0001*.md           # Research: what is information?
    ├── DISCUSSION-0002*.md           # Research: what should UIS scope?
    ├── DISCUSSION-0003*.md           # Research: canonical model feasibility
    ├── DISCUSSION-0004*.md           # Research: boundaries and interfaces
    ├── ARCHITECTURE-INSIGHT-0001*.md # Core architectural direction
    └── archive/                      # Previous work, placeholders
```

## Getting Started

1. Read [docs/ARCHITECTURE-INSIGHT-0001-information-mapping.md](docs/ARCHITECTURE-INSIGHT-0001-information-mapping.md) for the core idea
2. Review the discussions to understand the open questions
3. Check [docs/PROJECT-STATUS.md](docs/PROJECT-STATUS.md) for current state

## Participation

This is an early-stage research project. We're exploring ideas, not building a product.

To contribute:
- Read the discussion documents
- Share feedback on the approach
- Suggest additional research directions

See [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines.

## License

Apache License 2.0 — see [LICENSE](LICENSE)
