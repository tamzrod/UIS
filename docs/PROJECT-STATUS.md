# UIS Project Status

**Last Updated**: 2026-07-18

## Maturity Level

**Stage**: Early research and design

This is not a mature specification. We are exploring fundamental questions before committing to technical decisions.

## What Has Been Established

### Core Architecture

We have identified a promising architectural direction: **information mapping**.

The core insight is that UIS should map information from original artifacts into a canonical structure—without modifying the originals. This approach:

- Preserves source fidelity
- Enables interoperability through structure
- Supports multiple views of the same data
- Maintains traceability to sources

See [ARCHITECTURE-INSIGHT-0001-information-mapping.md](ARCHITECTURE-INSIGHT-0001-information-mapping.md)

### Foundational Concepts

We have a draft scope, terms, and design principles:

| Document | Status | Notes |
|----------|--------|-------|
| 001-scope.md | Draft | Defines UIS field of application |
| 003-terms-and-definitions.md | Draft | Key terminology |
| 004-design-principles.md | Draft | Core principles |
| 005-architecture.md | Draft | High-level framework |

### Research Progress

We have completed four research discussions:

| Document | Question | Status |
|----------|----------|--------|
| DISCUSSION-0001 | What is information? | Complete |
| DISCUSSION-0002 | What should UIS scope? | Complete |
| DISCUSSION-0003 | Can one model represent everything? | Complete |
| DISCUSSION-0004 | What are UIS boundaries? | Complete |

### Working Hypotheses

Based on research, we have provisional hypotheses:

1. **Universal structure is feasible**: A single canonical model may represent information from all analyzed domains.

2. **Information primitives are identifiable**: Entity, property, value, relationship, identity, type appear universal.

3. **Artifact preservation is fundamental**: Original artifacts should remain unchanged.

4. **Mapping non-standardization is acceptable**: How information is extracted matters less than the resulting structure.

## What Remains Unknown

### Core Uncertainties

| Question | Impact | Blocker? |
|----------|--------|----------|
| What is the minimal mandatory core? | High | Yes |
| How should truth and evidence be handled? | High | Yes |
| Should UIS include optional semantic layers? | Medium | No |
| How should extensions be identified? | Medium | No |
| What conformance tiers are needed? | Medium | No |

### Design Decisions Pending

These questions require architectural decisions before formal specification:

1. **Scope decision**: Information as primary scope (ADR-0001 pending)
2. **Core definition**: Minimal mandatory elements
3. **Truth handling**: Evidence-first approach vs. truth requirements
4. **Extension mechanism**: How domain-specific extensions work
5. **Identity system**: How records are identified

## Current Architectural Hypotheses

### Hypothesis 1: Information Mapping

> UIS does not replace or transform original artifacts. UIS maps information from artifacts into a canonical information model.

**Status**: Most promising direction, not yet decided

### Hypothesis 2: Minimal Universal Core

> The following elements are necessary and sufficient for all analyzed domains: Entity, Property, Value, Identifier, Type, Association, Containment, Temporal, Provenance.

**Status**: Not falsified by 11-domain analysis

### Hypothesis 3: Artifact Preservation

> Original artifacts should never be modified or converted by UIS processes.

**Status**: Seems fundamental, not controversial

### Hypothesis 4: Evidence-First

> UIS structures should support evidence representation before conclusions.

**Status**: Promising but requires more analysis

## Next Milestones

### Immediate (Current Branch)

- [x] Complete foundational discussions
- [x] Establish architectural direction
- [ ] ~~Formal architectural decisions~~ (deferred)
- [ ] ~~Specification drafting~~ (deferred)

### Near-Term

1. Resolve ADR-0001 (UIS Scope)
2. Define minimal canonical record structure
3. Create reference examples from domain artifacts
4. Draft conformance requirements

### Long-Term

1. Progress from Working Draft to formal specification
2. Develop reference implementations
3. Establish community review process
4. Publish first stable version

## What's Not Happening

This is an early-stage research project. We are not:

- Building software
- Creating schemas
- Defining APIs
- Writing database designs
- Publishing formal specifications
- Certifying implementations

We are exploring ideas and understanding the problem space.

## How to Follow Progress

| Resource | Purpose |
|----------|---------|
| README.md | Project overview |
| PROJECT-STATUS.md | This document |
| docs/ARCHITECTURE-INSIGHT-0001*.md | Core direction |
| docs/DISCUSSION-*.md | Research explorations |
| docs/archive/ | Previous work |

## Contributing

We welcome feedback on the architectural direction. See [CONTRIBUTING.md](../CONTRIBUTING.md) for how to participate.

---

*This document reflects the current state of an exploratory research project. Content is subject to change.*
