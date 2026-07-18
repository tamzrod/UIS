# UIS Project Status

**Last Updated**: 2026-07-18

## Maturity Level

**Stage**: Early research and design

This is not a mature specification. We are exploring fundamental questions before committing to technical decisions.

## What Has Been Established

### Core Clarification

UIS defines the canonical structure for representing extracted information.

UIS does NOT define how information is extracted, stored, or consumed.

```
Extraction → [UIS] → Storage/Consumption
     ↑          ↓              ↑
   Outside    UIS           Outside
```

This scope clarification establishes:
- Single responsibility: record structure only
- Extraction independence: any method works
- Storage independence: any system works
- Consumer independence: any application works

See [ARCHITECTURE-INSIGHT-0001-information-mapping.md](ARCHITECTURE-INSIGHT-0001-information-mapping.md)

### Foundational Concepts

We have a draft scope, terms, and design principles:

| Document | Status | Notes |
|----------|--------|-------|
| 001-scope.md | Draft | Defines UIS scope and boundaries |
| 003-terms-and-definitions.md | Draft | Key terminology |
| 004-design-principles.md | Draft | Core principles |

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

1. **Canonical structure is feasible**: A single model may represent extracted information from all analyzed domains.

2. **Record primitives are identifiable**: Identity, classification, content, relationships, provenance appear universal.

3. **Extraction independence is correct**: How information is extracted is outside UIS scope.

4. **Source provenance is required**: Records must reference source artifacts.

## What Remains Unknown

### Core Uncertainties

| Question | Impact | Blocker? |
|----------|--------|----------|
| What is the minimal mandatory record structure? | High | Yes |
| How should relationships be structured? | High | Yes |
| Should provenance be mandatory? | Medium | No |
| How should extensions be identified? | Medium | No |
| What conformance tiers are needed? | Medium | No |

### Design Decisions Pending

These questions require architectural decisions before formal specification:

1. **Record structure**: Define mandatory and optional elements
2. **Identity system**: How records are uniquely identified
3. **Relationship model**: How records connect
4. **Provenance requirements**: Mandatory vs. optional
5. **Extension mechanism**: How domain-specific types work

## Next Milestones

### Near-Term

1. Define minimal canonical record structure
2. Create examples from domain artifacts
3. Draft conformance requirements
4. Establish research validation

### Long-Term

1. Progress from Working Draft to formal specification
2. Develop reference implementations
3. Establish community review process
4. Publish first stable version

## What's Not Happening

This is an early-stage research project. We are not:

- Building extraction systems
- Creating storage systems
- Defining search engines
- Building AI systems
- Publishing formal specifications

We are exploring what a canonical record structure should contain.

## How to Follow Progress

| Resource | Purpose |
|----------|---------|
| README.md | Project overview |
| docs/PROJECT-STATUS.md | This document |
| docs/ARCHITECTURE-INSIGHT-0001*.md | Scope clarification |
| docs/DISCUSSION-*.md | Research explorations |

## Contributing

We welcome feedback on the scope clarification. See [CONTRIBUTING.md](../CONTRIBUTING.md) for how to participate.

---

*This document reflects the current state of an exploratory research project. Content is subject to change.*
