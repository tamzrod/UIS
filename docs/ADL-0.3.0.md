# UIS Working Draft 0.3.0 — Architectural Decision Log

**Document Date**: 2026-07-18
**Source**: Editorial Review Report (REVIEW-0.3.0.md)
**Status**: Pending Committee Review
**Decisions Required**: 8
**Decisions Deferred**: 10

---

## Decision Framework

Each issue has been reclassified as one of:

| Classification | Definition | Resolution Authority |
|---------------|------------|---------------------|
| **Editorial** | Grammar, phrasing, clarity | Editor |
| **Structural** | Internal document consistency | Document Author |
| **Normative** | Conformance requirements | Committee Vote |
| **Fundamental Design Decision (FDD)** | Core architectural choices affecting specification scope | Consensus Required |

---

## DECISIONS REQUIRED

These issues represent architectural choices that require explicit committee approval.

---

### DECISION-001: Encoding Scope Boundary

**Source Issue**: N-001 (Architecture) + N-003 (Design Principles)

**Original Classification**: Normative

**Reclassified As**: **Fundamental Design Decision**

**Documents Affected**:
- 001 Scope
- 004 Design Principles
- 005 Architecture

**Issue Statement**:
The current specification contains contradictory positions:
- 001 Scope Section 4.a: Excludes "specific file formats, data structures, or encoding schemes"
- 005 Architecture Section 2.3: States UIS "defines requirements that encodings SHALL satisfy"
- 004 Design Principles Section 2.5: States UIS "should enable mapping between different encoding schemes"

**Architectural Implication**:
UIS must choose one of three positions regarding encoding:

| Position | Implication |
|----------|-------------|
| **Encoding-Agnostic** | UIS makes no statements about encodings; implementations may use any format |
| **Encoding-Conscious** | UIS defines abstract requirements that encodings SHOULD satisfy; allows but does not mandate compliance |
| **Encoding-Prescriptive** | UIS mandates specific encoding requirements for conformance |

**Downstream Impact**:
- 006 Information Model: Depends on whether model defines encoding-independent constraints
- 007 General Requirements: May include encoding-related requirements
- 008 Identity: Identifier syntax may depend on encoding choice

**Resolution Options**:

**Option A — Encoding-Agnostic (Recommended)**
```
Remove all encoding references from UIS.
Scope: Add to Section 4: "h) Encoding requirements"
Architecture: Rewrite Section 2.3 to exclude encoding requirements entirely
Design Principles: Remove "encoding schemes" from Section 2.5 implications
```
*Rationale*: Maximizes domain neutrality; UIS becomes truly implementation-independent

**Option B — Encoding-Conscious**
```
UIS defines abstract encoding requirements without mandating specific formats.
Scope: Modify Section 4.a to exclude specific formats only
Architecture: Retain Section 2.3 with "SHOULD" instead of "SHALL"
Design Principles: Retain Section 2.5 with clarification
```
*Rationale*: Provides guidance without prescription; moderate complexity

**Option C — Encoding-Prescriptive**
```
UIS mandates encoding requirements for conformance.
Scope: Remove encoding from Section 4 entirely
Architecture: Strengthen Section 2.3 with specific requirements
Design Principles: Elevate encoding support to mandatory
```
*Rationale*: Enables interoperability at encoding level; limits domain flexibility

---

### DECISION-002: Profile Normative Status

**Source Issue**: N-002 (Architecture)

**Original Classification**: Normative

**Reclassified As**: **Fundamental Design Decision**

**Documents Affected**:
- 005 Architecture

**Issue Statement**:
Application Layer profiles are classified as informative components. However, profiles that constrain conformance requirements are inherently normative.

**Architectural Implication**:
The classification determines whether profile compliance is required or optional.

**Downstream Impact**:
- 007 General Requirements: May reference profile conformance
- 012 Conformance: Profile conformance testing procedures depend on this classification

**Resolution Options**:

**Option A — Profiles Are Normative**
```
All UIS profiles are normative. Conformance to a profile requires satisfying all profile requirements.
Architecture: Move profiles to Section 5.1 (Normative Components)
```
*Rationale*: Ensures profile requirements are binding; matches industry practice (e.g., W3C, IETF)*

**Option B — Profiles Have Dual Nature**
```
Some profiles are normative (constraining conformance); others are informative (providing guidance).
Architecture: Divide Section 5 into three categories: Normative, Informative, Conformance Profiles
```
*Rationale*: Distinguishes guidance profiles from conformance profiles; requires clear criteria

**Option C — Profiles Remain Informative**
```
Profiles provide guidance but do not create conformance requirements.
Architecture: Clarify Section 5.2 to explicitly state profiles are non-binding
```
*Rationale*: Maintains current text; requires additional language to prevent misunderstanding

---

### DECISION-003: Principle Hierarchy Interpretation

**Source Issue**: N-004 (Design Principles)

**Original Classification**: Normative

**Reclassified As**: **Fundamental Design Decision**

**Documents Affected**:
- 004 Design Principles

**Issue Statement**:
Section 4 (Principle Hierarchy) presents five principles with inconsistent language:
- Items 1-2 use descriptive language ("takes precedence")
- Item 3 uses mandatory language ("shall not be compromised")
- Item 5 states "primary objective" while numbered #5

**Architectural Implication**:
The hierarchy determines how conflicts between principles are resolved. The current inconsistent presentation creates ambiguity about which principle takes precedence in genuine conflicts.

**Downstream Impact**:
- 006 Information Model: Decisions about model expressiveness
- 007 General Requirements: May reference principle precedence
- 011 Provenance: Traceability vs. simplicity trade-offs

**Resolution Options**:

**Option A — Principles as Constraints (Strict Hierarchy)**
```
All principles are mandatory constraints. When principles conflict, the hierarchy strictly applies.
Design Principles: Use consistent SHALL language; clarify #5 is highest priority
```
*Rationale*: Provides clear resolution mechanism; may be too rigid*

**Option B — Principles as Guidelines (Weighted Considerations)**
```
All principles are important; the hierarchy provides guidance but not strict precedence.
Design Principles: Use SHOULD language; clarify hierarchy as "considerations" not rules
```
*Rationale*: Allows case-by-case judgment; may lead to inconsistent interpretation*

**Option C — Principles as Independent (No Hierarchy)**
```
Principles are independent requirements; conflicts require explicit resolution per-case.
Design Principles: Remove hierarchy section entirely; document conflicts in relevant clauses
```
*Rationale*: Avoids false precision; requires more documentation*

---

### DECISION-004: Schema Definition Requirement

**Source Issue**: N-005 (Terms and Definitions)

**Original Classification**: Normative

**Reclassified As**: **Fundamental Design Decision**

**Documents Affected**:
- 003 Terms and Definitions
- 006 Information Model

**Issue Statement**:
"Schema" is used in the definition of "structured information" but is not defined in UIS.

**Architectural Implication**:
The term "schema" implies a structural constraint mechanism. The specification must decide whether UIS defines its own schema concept or defers to external definitions.

**Downstream Impact**:
- 006 Information Model: Schema is a core structural concept
- 007 General Requirements: May reference schema requirements
- 010 Relationships: Schema may constrain relationship declarations

**Resolution Options**:

**Option A — Define Schema in UIS**
```
Add "schema" to Terms and Definitions as a normative term.
Terms: "schema: A formal specification that defines the structure of information within a model"
```
*Rationale*: Complete terminology; enables conformance testing*

**Option B — Reference External Definition**
```
Add informative reference to external schema standards (e.g., ISO/IEC 11179).
Terms: "schema: As defined in [external reference]"
```
*Rationale*: Avoids redefining established concepts; requires external dependency*

**Option C — Remove Schema Term**
```
Revise "structured information" definition to avoid "schema."
Terms: "Information that has been organized according to a defined information model"
```
*Rationale*: Simplifies terminology; defers schema concept to Information Model*

---

### DECISION-005: State Definition Requirement

**Source Issue**: N-006 (Terms and Definitions)

**Original Classification**: Normative

**Reclassified As**: **Fundamental Design Decision**

**Documents Affected**:
- 003 Terms and Definitions
- 010 Versioning
- 013 Versioning

**Issue Statement**:
"Version" is defined using "state," which is not defined and carries computational connotations.

**Architectural Implication**:
UIS must decide whether "state" is a valid abstract concept or whether versioning should use alternative terminology.

**Downstream Impact**:
- 010 Versioning: Core versioning concepts depend on this terminology
- 013 Versioning: Version lifecycle may reference state transitions

**Resolution Options**:

**Option A — Define State as Abstract Concept**
```
Add "state" to Terms and Definitions.
Terms: "state: A condition or mode of existence of an entity at a given time"
```
*Rationale*: Establishes terminology; abstract enough for domain neutrality*

**Option B — Replace with Alternative Terminology**
```
Revise "version" definition to avoid "state."
Terms: "version: A distinct manifestation of an entity that can be distinguished from other manifestations of the same entity"
```
*Rationale*: Avoids potentially loaded terminology; simpler definition*

**Option C — Defer to Versioning Document**
```
Remove "state" reference; note that "version" semantics are defined in 010 Versioning.
Terms: "version: As defined in Clause 010"
```
*Rationale*: Defers complexity; defers terminology definition*

---

### DECISION-006: System Design Scope Inclusion

**Source Issue**: N-007 (Scope)

**Original Classification**: Normative

**Reclassified As**: **Fundamental Design Decision**

**Documents Affected**:
- 001 Scope

**Issue Statement**:
Scope includes "design of systems" (Section 2.c) but excludes "storage technologies" (Section 4.g), creating ambiguity about what system design aspects are included.

**Architectural Implication**:
UIS must clarify whether it addresses system-level concerns or remains strictly at the information representation level.

**Downstream Impact**:
- 005 Architecture: Representation Layer scope depends on this decision
- 007 General Requirements: System-level requirements may or may not apply
- All downstream documents: Scope boundaries affect applicability

**Resolution Options**:

**Option A — Systems Within Scope**
```
UIS addresses information system design principles.
Scope: Clarify Section 2.c; modify Section 4.g to specify "specific storage technologies" only
```
*Rationale*: Aligns with broad applicability goal; increases complexity*

**Option B — Systems Outside Scope**
```
UIS addresses information representation only, not system design.
Scope: Remove Section 2.c entirely; clarify Section 4.g
```
*Rationale*: Strict domain neutrality; clearer boundaries*

**Option C — Hybrid Approach**
```
UIS addresses system interfaces but not internal design.
Scope: Add clarifying language to Section 2.c specifying "information system interfaces"
```
*Rationale*: Balances applicability and scope; requires careful wording*

---

### DECISION-007: Circular Definition Resolution Method

**Source Issue**: S-001 (Terms and Definitions)

**Original Classification**: Structural

**Reclassified As**: **Normative** (requires terminology standard)

**Documents Affected**:
- 003 Terms and Definitions

**Issue Statement**:
"Relationship" is defined as "connection or association" — terms that are effectively synonymous.

**Architectural Implication**:
The specification requires a methodology for resolving circular definitions that may apply to other terms as well.

**Downstream Impact**:
- All term definitions: Methodology applies to future definitions
- 008 Identity: Relationship between entities
- 010 Relationships: Relationship types (meta-circular concern)

**Resolution Options**:

**Option A — Operational Definition**
```
Redefine: "A directed link between entities, characterized by a relationship type, that expresses a meaningful connection"
```
*Rationale*: Uses "link" (more specific); introduces relationship type*

**Option B — Set-Theoretic Definition**
```
Redefine: "A tuple (source, target, type) that represents a meaningful connection between entities"
```
*Rationale*: Formal definition; enables computational modeling*

**Option C — Axiomatic Approach**
```
Retain current definition; note in Scope that certain terms are primitive
Terms: "relationship: A primitive concept; the exact nature of relationships is defined axiomatically in 008 Relationships"
```
*Rationale*: Accepts circularity at foundational level; defines semantics later*

---

### DECISION-008: Extension Point Taxonomy

**Source Issue**: S-004 (Architecture)

**Original Classification**: Structural

**Reclassified As**: **Fundamental Design Decision**

**Documents Affected**:
- 005 Architecture
- 006 Information Model
- 007 General Requirements

**Issue Statement**:
Extension points are inconsistently categorized (type, property, relationship, profile) without a clear taxonomic framework.

**Architectural Implication**:
The taxonomy determines what can be extended and how extensions relate to the core model.

**Downstream Impact**:
- 006 Information Model: Extension mechanisms for types and properties
- 007 General Requirements: Extension-related requirements
- 008 Identity: Identifier extension mechanisms
- 010 Relationships: Relationship extension mechanisms

**Resolution Options**:

**Option A — Three-Level Taxonomy**
```
Extensions are categorized by scope:
- Core Extensions: Modify fundamental UIS concepts
- Model Extensions: Add new types, properties, relationships
- Profile Extensions: Constrain or specialize for domains
```
*Rationale*: Clear hierarchy; matches proposed architecture layers*

**Option B — Two-Level Taxonomy**
```
Extensions are categorized by conformance impact:
- Normative Extensions: Affect conformance requirements
- Informative Extensions: Provide guidance without conformance impact
```
*Rationale*: Aligns with normative/informative distinction; simpler*

**Option C — Unified Extension Model**
```
All extensions follow the same mechanism; only identification differs.
Architecture: Define single extension framework; taxonomy based on what is extended
```
*Rationale*: Uniform treatment; requires consistent extension syntax*

---

## DECISIONS DEFERRED

These issues do not require immediate committee action and may be resolved by the editor or document author.

---

### DEFERRED-001: Classification Terminology (S-002)

**Classification**: Editorial
**Resolution Authority**: Editor
**Action**: Define "classification" or revise definition of "type"

---

### DEFERRED-002: Origin vs. Provenance (S-003)

**Classification**: Structural
**Resolution Authority**: Document Author
**Action**: Replace "origin" with "provenance" in Design Principles

---

### DEFERRED-003: Agent Examples Neutrality (S-005)

**Classification**: Structural
**Resolution Authority**: Document Author
**Action**: Provide domain-neutral examples or define agent by capability

---

### DEFERRED-004: Specification Organization Table (S-006)

**Classification**: Structural
**Resolution Authority**: Document Author
**Action**: Expand table or provide mapping reference

---

### DEFERRED-005: Structuring vs. Organizing (E-001)

**Classification**: Editorial
**Resolution Authority**: Editor
**Action**: Consider "organizing" instead of "structuring" in Scope

---

### DEFERRED-006: Representation Definition Alignment (E-002)

**Classification**: Editorial
**Resolution Authority**: Editor
**Action**: Align definition with Note: "manifestation" instead of "form"

---

### DEFERRED-007: Interoperability Exchange Assumption (E-003)

**Classification**: Editorial
**Resolution Authority**: Editor
**Action**: Consider alternative wording avoiding "exchange"

---

### DEFERRED-008: Information Object Structure Requirement (E-004)

**Classification**: Editorial
**Resolution Authority**: Document Author
**Action**: Consider allowing unstructured information objects

---

### DEFERRED-009: Component Terminology (E-005)

**Classification**: Editorial
**Resolution Authority**: Editor
**Action**: Consider "constituent elements" instead of "components"

---

### DEFERRED-010: Relationship Extension Consistency (S-004)

**Classification**: Structural (Note: Superseded by DECISION-008)
**Resolution Authority**: Committee (via DECISION-008)

---

## Summary Table

| ID | Issue | Classification | Authority | Status |
|----|-------|---------------|-----------|--------|
| DECISION-001 | Encoding Scope | FDD | Committee | **Required** |
| DECISION-002 | Profile Status | FDD | Committee | **Required** |
| DECISION-003 | Principle Hierarchy | FDD | Committee | **Required** |
| DECISION-004 | Schema Definition | FDD | Committee | **Required** |
| DECISION-005 | State Definition | FDD | Committee | **Required** |
| DECISION-006 | System Scope | FDD | Committee | **Required** |
| DECISION-007 | Circular Definition | Normative | Committee | **Required** |
| DECISION-008 | Extension Taxonomy | FDD | Committee | **Required** |
| DEFERRED-001 to 009 | Various | Editorial/Structural | Editor/Author | Deferred |

---

## Voting Requirements

For advancement to Working Draft 0.4.0, the following decisions require committee approval:

1. **DECISION-001**: Encoding Scope Boundary
2. **DECISION-002**: Profile Normative Status
3. **DECISION-003**: Principle Hierarchy Interpretation
4. **DECISION-004**: Schema Definition Requirement
5. **DECISION-005**: State Definition Requirement
6. **DECISION-006**: System Design Scope Inclusion
7. **DECISION-007**: Circular Definition Resolution Method
8. **DECISION-008**: Extension Point Taxonomy

Approval requires consensus of the committee or a defined majority vote per the Decision Process (governance/002-decision-process.md).

---

*This document was generated from REVIEW-0.3.0.md as part of the UIS Working Draft 0.3.0 development process.*
