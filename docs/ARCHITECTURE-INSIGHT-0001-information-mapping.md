# ARCHITECTURE-INSIGHT-0001: The UIS Scope Boundary

**Document Number**: ARCHITECTURE-INSIGHT-0001
**Title**: Clarifying What UIS Actually Standardizes
**Status**: Exploratory — Architectural Insight
**Date**: 2026-07-18
**Author**: UIS Working Group
**Related**:
- DISCUSSION-0001: What is Information?
- DISCUSSION-0002: Scope of UIS
- DISCUSSION-0003: Canonical Information Model
- DISCUSSION-0004: Boundaries of UIS

---

## 1. The Core Clarification

### 1.1 The Key Insight

Through analysis of what UIS should and should not scope, a fundamental clarification has emerged:

> **UIS defines the canonical representation of extracted information. UIS does not define how information is extracted, stored, or consumed.**

This means:

| Concern | Who Defines It |
|---------|---------------|
| Extraction | Outside UIS (parsers, OCR, AI, humans) |
| Canonical Representation | **UIS** |
| Storage | Outside UIS (databases, files) |
| Consumption | Outside UIS (search, analytics, AI) |

### 1.2 Why This Scope is Correct

The scope boundary is fundamental because:

1. **Separation of Concerns**: Extraction, representation, storage, and consumption are independent concerns that evolve at different rates.

2. **Enables Interoperability**: A common representation enables any extractor to produce records that any consumer can understand.

3. **Preserves Choice**: Organizations can choose their own extraction methods, storage systems, and applications while still achieving interoperability.

4. **Single Responsibility**: UIS focuses on one thing—defining the canonical record structure—rather than trying to be everything to everyone.

### 1.3 What This Means

UIS is NOT:
- An ingestion framework
- An ETL pipeline
- An OCR system
- A parser
- An AI system
- A database
- A search engine
- An investigation platform
- An application

UIS IS:
- A specification for the structure of information records
- A vocabulary for describing information
- A set of principles for representing information
- A conformance framework for information representations

---

## 2. The Scope Boundary

### 2.1 Architecture Overview

```
┌─────────────────────────────────────────────────────────────┐
│                         OUTSIDE UIS                          │
│           EXTRACTION / INGESTION LAYER                      │
│  (PDF parsing, OCR, AI, rule-based extraction, human review) │
│  ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ │
│  This layer is NOT standardized by UIS.                     │
│  Any extraction method may produce UIS-conformant records.  │
└─────────────────────────────────────────────────────────────┘
                              │
                              ▼
═══════════════════════════════════════════════════════════════
                    UIS STANDARDIZES THIS
═══════════════════════════════════════════════════════════════
┌─────────────────────────────────────────────────────────────┐
│            CANONICAL INFORMATION RECORD LAYER                │
│                                                              │
│  ┌──────────────────────────────────────────────────────┐  │
│  │  Identity  │  Classification  │  Content              │  │
│  │  Provenance (→ source artifact)  │  Relationships      │  │
│  └──────────────────────────────────────────────────────┘  │
│                                                              │
│  ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━  │
│  UIS defines the STRUCTURE of information records only.     │
│  UIS does not define how records are extracted or stored.   │
└─────────────────────────────────────────────────────────────┘
═══════════════════════════════════════════════════════════════
═══════════════════════════════════════════════════════════════
                              │
                              ▼
┌─────────────────────────────────────────────────────────────┐
│                         OUTSIDE UIS                          │
│              CONSUMPTION LAYER                               │
│         (Databases, search, analytics, AI, apps)            │
│  ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ │
│  This layer is NOT standardized by UIS.                     │
│  Any consumer may read UIS-conformant records.              │
└─────────────────────────────────────────────────────────────┘
```

### 2.2 Layer Responsibilities

#### Extraction Layer (Outside UIS)

**Description**: The process of extracting information from original sources.

**Responsibilities**:
- Interprets source content
- Extracts relevant information elements
- Produces UIS-conformant records
- May be performed by parsers, AI, rule-based systems, or humans

**Examples**: PDF parser, OCR system, AI extractor, human reviewer

**Note**: The extraction process is NOT standardized by UIS.

#### Canonical Information Record Layer (UIS)

**Description**: The UIS-conformant representation of extracted information.

**Responsibilities**:
- Provides a universal structure for information
- References source artifacts (provenance)
- Enables interoperability across domains
- Serves as the contract between extractors and consumers

**Note**: This is EXACTLY what UIS standardizes.

#### Consumption Layer (Outside UIS)

**Description**: Systems that store, search, analyze, or otherwise use information records.

**Responsibilities**:
- Stores records in any system
- Performs search and retrieval
- Applies analytics and AI
- Generates new records (from analysis)

**Examples**: Databases, search engines, analytics platforms, AI systems, applications

**Note**: How records are consumed is NOT standardized by UIS.

---

## 3. Source Artifact Principle

### 3.1 The Principle

> **Canonical records reference source artifacts. UIS does not require modification or preservation of original artifacts.**

This principle has several implications:

1. **No Forced Transformation**: UIS does not require organizations to modify their source artifacts. Artifacts remain in their native form.

2. **Reference, Not Replication**: UIS records contain references to original artifacts, not copies of artifact content.

3. **Provenance Required**: Every canonical record should reference its source artifact, enabling traceability.

4. **Artifact Independence**: Source artifacts may be in any format, stored anywhere, managed by any system.

### 3.2 Artifact Examples

The following examples illustrate source artifacts across diverse domains:

| Domain | Artifact Type | Example Extractors |
|--------|---------------|-------------------|
| Documents | PDF | PDF parser, text extractor |
| Industrial | COMTRADE | Sensor system, data logger |
| Imaging | JPEG | Camera, scanner |
| Medical | DICOM | Imaging modality |
| Communications | Email | Mail server |
| Manufacturing | PLC Tags | PLC, SCADA |
| Databases | Records | Database system |
| Audio | WAV/MP3 | Audio recorder |
| Video | MP4 | Video recorder |
| Legal | Contracts | Document system |

**Note**: These extractors are OUTSIDE UIS. UIS only standardizes the structure of the extracted records.

---

## 4. Extraction Independence Principle

### 4.1 The Principle

> **UIS standardizes the structure of information records, not how information is extracted.**

This principle separates two distinct concerns:

| Concern | Standardized by UIS? |
|---------|---------------------|
| How information is extracted | **NO** |
| The structure of extracted information | **YES** |

### 4.2 Extraction Methods

Information can be extracted from artifacts through any means:

| Method | Examples |
|--------|----------|
| Human interpretation | Expert review, manual data entry |
| Artificial Intelligence | NLP, computer vision, LLMs |
| Rule-based extraction | Regex, schema mapping, business rules |
| Format parsers | JSON parser, XML parser, CSV reader |
| Vendor connectors | SAP connector, Salesforce connector |

### 4.3 What UIS Does NOT Standardize

UIS does NOT standardize:
- Extraction methods or tools
- AI model architectures
- Parser implementations
- Human qualifications
- Quality of extraction

### 4.4 What UIS DOES Standardize

UIS DOES standardize:
- The structure of canonical information records
- Required and optional elements
- Relationship types
- Identity requirements
- Provenance (reference to source artifact)

---

## 5. Canonical Information Record

### 5.1 Concept Overview

A **canonical information record** is the UIS-conformant representation of extracted information. It is the ONLY thing UIS standardizes.

The canonical record is:
- **Independent**: Works with any extraction method
- **Structured**: Organized according to UIS specification
- **Traceable**: References source artifacts
- **Extensible**: Supports domain-specific extensions
- **Interoperable**: Enables cross-domain information exchange

### 5.2 Candidate Universal Elements

The following elements are candidates for the canonical record structure:

| Element | Purpose | Standardized by UIS? |
|---------|---------|---------------------|
| Identity | Unique identification of record | **YES** |
| Classification | Type/category of record | **YES** |
| Content | The extracted information | **YES** |
| Relationships | Connections to other records | **YES** |
| Provenance | Reference to source artifact | **YES** |
| Evidence | Supporting evidence | Optional |
| Confidence | Reliability indicator | Optional |
| Version | Change tracking | Optional |

### 5.3 Elements UIS Standardizes

These elements define the structure of canonical records:

- **Identity**: How records are uniquely identified
- **Classification**: How records are categorized
- **Content**: How extracted information is represented
- **Relationships**: How records connect to each other
- **Provenance**: How records reference source artifacts

---

## 6. Separation of Concerns

### 6.1 Clear Boundaries

The architecture achieves clarity through strict separation:

| Concern | Responsibility | Standardized by UIS? |
|---------|---------------|---------------------|
| Extraction | Outside UIS | NO |
| Record Structure | UIS | **YES** |
| Storage | Outside UIS | NO |
| Search | Outside UIS | NO |
| Analytics | Outside UIS | NO |
| AI Reasoning | Outside UIS | NO |

### 6.2 What Each Party Does

#### Extraction Systems (Outside UIS)

- Parse documents, images, databases
- Run OCR, AI, NLP
- Extract information
- Produce UIS-conformant records

#### UIS Standard

- Defines record structure
- Specifies required elements
- Enables interoperability

#### Storage/Consumption Systems (Outside UIS)

- Store records in databases
- Build search indexes
- Apply analytics
- Run AI models

### 6.3 Concern Matrix

| Concern | Extraction | UIS Standard | Storage | Consumption |
|---------|------------|--------------|---------|-------------|
| Information extraction | ✓ | | | |
| Record structure | | ✓ | | |
| Storage mechanism | | | ✓ | |
| Search implementation | | | | ✓ |
| Analytics | | | | ✓ |

---

## 7. Core Principles

### 7.1 The Principles

Based on the scope clarification, the following principles guide UIS:

#### Extraction Independence

> UIS shall not define how information is extracted.

**Rationale**: Allows any extraction method (AI, OCR, parsers, humans) to produce conformant records.

#### Representation Focus

> UIS shall define only the structure of information records.

**Rationale**: Single responsibility keeps UIS focused and stable.

#### Source Provenance

> UIS records shall reference source artifacts.

**Rationale**: Enables traceability and trust in extracted information.

#### Domain Neutrality

> The canonical model shall be applicable across all domains.

**Rationale**: Enables universal interoperability and prevents fragmentation.

#### Implementation Independence

> UIS shall not depend on specific technologies, formats, or platforms.

**Rationale**: Ensures longevity and broad applicability.

#### Extensible Core

> The canonical model shall support domain-specific extensions without modification.

**Rationale**: Enables specialization while maintaining interoperability.

### 7.2 Principle Hierarchy

When principles conflict:

1. **Extraction Independence** (highest priority)
2. **Representation Focus**
3. **Source Provenance**
4. **Domain Neutrality**
5. **Implementation Independence**
6. **Extensible Core**

---

## 8. Implications

### 8.1 What This Scope Enables

| Benefit | How |
|---------|-----|
| Any extractor works | Extraction is outside UIS |
| Any storage works | Storage is outside UIS |
| Any consumer works | Consumption is outside UIS |
| Interoperability | All produce/consume same record structure |
| Longevity | UIS doesn't depend on extraction technology |

### 8.2 What This Scope Excludes

UIS does not address:

| Concern | Why Excluded |
|---------|--------------|
| Extraction quality | Varies by use case |
| Storage mechanism | Technology-specific |
| Search implementation | Use-case specific |
| AI reasoning | Outside representation scope |
| Business rules | Domain-specific |

### 8.3 Integration Points

UIS sits between extraction and consumption:

```
Extraction → [UIS] → Storage/Consumption
```

Any system at each layer can be swapped independently.

---

## 9. Open Questions

### 9.1 Record Structure Questions

**Q1**: What are the mandatory elements of a canonical record?

**Q2**: Should records include full extracted content or references to source artifacts?

**Q3**: How should relationships between records be structured?

### 9.2 Scope Questions

**Q4**: Should provenance be mandatory or optional?

**Q5**: Should UIS define extension mechanisms?

**Q6**: How should domain-specific types be accommodated?

### 9.3 Conformance Questions

**Q7**: What is required for a system to claim UIS conformance?

**Q8**: Does UIS conformance apply to extraction systems or only record structure?

### 9.4 Evolution Questions

**Q9**: How should UIS evolve without breaking existing records?

**Q10**: How should conflicts between record producers be handled?

---

## 10. Summary

### 10.1 The Core Clarification

UIS defines the canonical structure for representing extracted information. UIS does NOT define how information is extracted, stored, or consumed.

### 10.2 The Scope Boundary

```
Extraction → [UIS] → Storage/Consumption
     ↑          ↓              ↑
   Outside    UIS           Outside
```

### 10.3 Key Points

| Point | Description |
|-------|-------------|
| What UIS IS | Canonical record structure |
| What UIS is NOT | Extraction, storage, consumption |
| Who uses UIS | Extractor producers, consumer systems |
| Interoperability | Through shared record structure |

### 10.4 Status

This document clarifies the scope of UIS. It is exploratory and does not constitute a normative specification.

---

## References

1. UIS. (2026). *What is Information?* Discussion 0001. `docs/DISCUSSION-0001-information.md`

2. UIS. (2026). *Scope of UIS*. Discussion 0002. `docs/DISCUSSION-0002-scope-of-uis.md`

3. UIS. (2026). *Canonical Information Model*. Discussion 0003. `docs/DISCUSSION-0003-canonical-information-model.md`

4. UIS. (2026). *Boundaries of UIS*. Discussion 0004. `docs/DISCUSSION-0004-boundaries.md`

5. UIS. (2026). *Scope*. `docs/001-scope.md`

---

*This is an exploratory architectural insight document for UIS development. It does not constitute normative specification content.*
