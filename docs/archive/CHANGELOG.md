# Changelog

All notable changes to the Universal Information Standard (UIS) are documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [0.3.0] - 2026-07-18

### Authored

- [001 Scope](docs/001-scope.md) — Field of application, objectives, and boundaries
- [003 Terms and Definitions](docs/003-terms-and-definitions.md) — Essential vocabulary
- [004 Design Principles](docs/004-design-principles.md) — Core philosophy
- [005 Architecture](docs/005-architecture.md) — Conceptual layers and relationships

## [0.2.0] - 2026-07-18

### Added

- Architecture section ([#005](docs/005-architecture.md))
- General Requirements section ([#006](docs/006-general-requirements.md))
- Governance documents:
  - [Specification Lifecycle](governance/000-specification-lifecycle.md)
  - [Versioning Policy](governance/001-versioning-policy.md)
  - [Decision Process](governance/002-decision-process.md)
  - [Conformance Policy](governance/003-conformance-policy.md)

### Changed

- Renamed "Core Requirements" to "Fundamental Requirements" ([#007](docs/007-fundamental-requirements.md))
- Renumbered specification sections to accommodate Architecture
- Information Model moved to [#006](docs/006-information-model.md)

## [0.1.0] - 2026-07-18

### Changed

- Repository structure refactored to follow formal specification conventions
- Documentation reorganized into standards-style numbered sections

### Added

- Foreword section ([#000](docs/000-foreword.md))
- Scope section ([#001](docs/001-scope.md))
- Normative References section ([#002](docs/002-normative-references.md))
- Terms and Definitions section ([#003](docs/003-terms-and-definitions.md))
- Design Principles section ([#004](docs/004-design-principles.md))
- Information Model section ([#005](docs/005-information-model.md)) *(moved in 0.2.0)*
- Fundamental Requirements section ([#007](docs/007-fundamental-requirements.md))
- Identity section ([#008](docs/008-identity.md))
- Evidence section ([#009](docs/009-evidence.md))
- Relationships section ([#010](docs/010-relationships.md))
- Provenance section ([#011](docs/011-provenance.md))
- Conformance section ([#012](docs/012-conformance.md))
- Versioning section ([#013](docs/013-versioning.md))

### Removed

- Information Objects section (deferred until foundational concepts are established)

---

## Versioning

UIS follows a versioning scheme appropriate for formal standards:

- **Major version**: Introduces significant changes that may affect interoperability
- **Minor version**: Adds new capabilities without changing existing semantics
- **Patch version**: Clarifications, corrections, or editorial changes

See [Versioning](docs/013-versioning.md) for complete versioning policies.
