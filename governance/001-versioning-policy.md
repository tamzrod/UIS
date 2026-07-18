# Versioning Policy

## 1. General

This document defines the versioning scheme and policies for the Universal Information Standard (UIS). The versioning policy enables tracking of specification changes while supporting both single-author and collaborative development models.

## 2. Version Number Scheme

UIS uses semantic versioning adapted for standards:

```
<major>.<minor>.<patch>
```

| Component | Description | When to Increment |
|-----------|-------------|-------------------|
| **major** | Fundamental architectural changes | Breaking changes to normative content |
| **minor** | Added capabilities | New content that does not break existing conformance |
| **patch** | Corrections | Errors, clarifications, editorial changes |

### 2.1 Development Versions

During Working Draft stage, versions may include suffixes:

- `-alpha`: Early development
- `-beta`: Feature complete, testing
- `-rc.N`: Release candidate N

Examples: `0.3.0-alpha`, `0.4.0-rc.1`

## 3. Version Stage Indicators

Versions are associated with maturity stages:

| Stage | Indicator | Example |
|-------|-----------|---------|
| Working Draft | None or -alpha, -beta | `0.3.0`, `0.3.0-alpha` |
| Committee Draft | None | `0.5.0` |
| Proposed Standard | None | `1.0.0-ps` or `1.0.0` |
| Standard | None | `1.0.0` |

## 4. Change Classification

### 4.1 Major Changes

Major changes may break backward compatibility:

- Removal of mandatory requirements
- Changes to conformance definitions
- Fundamental architectural changes
- Changes that invalidate existing implementations

### 4.2 Minor Changes

Minor changes add content without breaking compatibility:

- New optional features
- New informative content
- New domain-specific guidance
- Clarifications that do not change requirements

### 4.3 Patch Changes

Patch changes correct errors:

- Typographical corrections
- Ambiguity resolution without changing meaning
- Cross-reference corrections
- Formatting improvements

## 5. Compatibility Policies

### 5.1 Within Major Version

Within the same major version, UIS maintains:

- **Backward compatibility**: New minor versions do not invalidate conformance to previous minor versions
- **Forward compatibility**: Implementations conforming to version N should function with version N+1

### 5.2 Major Version Transitions

Major version changes may break compatibility. Such changes require:

- Clear migration documentation
- Deprecation period when feasible
- Rationale documented in Architectural Decision Record

### 5.3 Deprecation

Deprecated features:

- Remain conformant for at least one minor version
- Are marked as deprecated in documentation
- Include guidance for migration

## 6. Applicability by Governance Model

### 6.1 Single Author

The author has full authority over versioning decisions. Changes are documented in the CHANGELOG.

### 6.2 Open Community

Version changes affecting normative content require documented Architectural Decision. Community input is sought through review processes.

### 6.3 Formal Organization

Version changes follow committee procedures. Compatibility impact is assessed per organizational policy.

## 7. Version Documentation

Each version release includes:

- CHANGELOG entry documenting changes
- Version indicator in specification header
- Reference to any Architectural Decision Records

## 8. Version References

Within UIS documents, references to other UIS specifications should include version:

- Current reference: `UIS v1.0.0`
- Version-agnostic reference: `UIS (any current version)`

When a specific feature is version-dependent, the required version shall be stated.
