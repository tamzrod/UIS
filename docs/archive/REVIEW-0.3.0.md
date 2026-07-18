# UIS Working Draft 0.3.0 — First Editorial Review

**Review Date**: 2026-07-18
**Review Status**: Initial Committee Review
**Documents Reviewed**:
- 001 Scope
- 003 Terms and Definitions
- 004 Design Principles
- 005 Architecture

---

## Executive Summary

This review identifies 18 issues across the four authored documents. Issues are classified as:

| Classification | Count | Severity |
|---------------|-------|----------|
| Normative | 7 | Requires resolution before advancement |
| Structural | 6 | Should be addressed |
| Editorial | 5 | Recommended improvements |

The documents demonstrate good adherence to standards writing style but require corrections to resolve internal contradictions, remove premature abstractions, and clarify ambiguous definitions.

---

## Issue Register

### NORMATIVE ISSUES

---

**Issue N-001**

**Document**: 005 Architecture, Section 2.3 (Representation Layer)

**Classification**: Normative

**Description**: The Representation Layer states that UIS "defines requirements that encodings SHALL satisfy," while 001 Scope explicitly excludes "Specific encodings" from scope (Section 4.a).

**Concern**: This constitutes a direct contradiction. Either UIS defines encoding requirements (within scope) or it does not (out of scope). The current text suggests both positions simultaneously.

**Recommendation**: Clarify the relationship between UIS and encodings. Consider one of:
- UIS defines abstract requirements that encodings SHOULD satisfy (permissive)
- UIS defines minimal requirements for conformance compliance (prescriptive)
- UIS does not define encoding requirements but provides guidance (informative)

---

**Issue N-002**

**Document**: 005 Architecture, Section 5.2 (Informative Components)

**Classification**: Normative

**Description**: Application Layer profiles are classified as informative components. However, profiles typically constrain conformance requirements and are therefore normative by nature.

**Concern**: Misclassification may lead to implementations treating profile requirements as optional when they should be mandatory for conformance to that profile.

**Recommendation**: Reclassify Application Layer profiles as normative components, or clarify that only certain profile types are informative.

---

**Issue N-003**

**Document**: 004 Design Principles, Section 2.5 (Interoperability)

**Classification**: Normative

**Description**: The principle states that UIS "should enable mapping between different encoding schemes." However, 001 Scope explicitly excludes "Specific encodings" from scope.

**Concern**: The principle implies UIS has opinions about encodings, contradicting the scope exclusion.

**Recommendation**: Remove reference to encoding schemes, or revise to address mapping at the conceptual or structural level only.

---

**Issue N-004**

**Document**: 004 Design Principles, Section 4 (Principle Hierarchy)

**Classification**: Normative

**Description**: The hierarchy mixes mandatory language ("shall not be compromised") with descriptive statements ("takes precedence over"). Item 5 states "Interoperability is the primary objective" but item 1-4 use hierarchical numbering suggesting a priority order.

**Concern**: The hierarchical numbering implies interoperability (#5) is the lowest priority, contradicting the statement that it is "primary." The SHALL language in item 3 creates ambiguity about whether other items are discretionary.

**Recommendation**: 
- Revise to use consistent language (e.g., "primary," "critical," "essential")
- Clarify whether the numbered list represents a strict priority or weighted considerations
- Ensure all mandatory principles use SHALL language

---

**Issue N-005**

**Document**: 003 Terms and Definitions, Section 2.3 (structured information)

**Classification**: Normative

**Description**: The term "structured information" is defined as information organized "according to a defined model or schema," but "schema" is not defined as a term in this document.

**Concern**: The definition relies on an undefined term, making conformance testing impossible. What constitutes a valid "schema"?

**Recommendation**: Either define "schema" or revise the definition to avoid the term. Consider: "Information that has been organized according to a defined information model."

---

**Issue N-006**

**Document**: 003 Terms and Definitions, Section 7.1 (version)

**Classification**: Normative

**Description**: The term "version" is defined as "a specific state of an entity at a point in time," but "state" is not defined.

**Concern**: "State" is a loaded term that may imply specific computational concepts (state machines, stateful systems). The relationship between "state" and "version" is unclear.

**Recommendation**: Define "state" or replace with clearer language such as: "A specific manifestation of an entity that can be distinguished from other manifestations of the same entity."

---

**Issue N-007**

**Document**: 001 Scope, Section 2.c

**Classification**: Normative

**Description**: Scope includes "The design of systems that create, process, store, or transmit information," but Section 4.g excludes "Storage technologies."

**Concern**: "Storage" appears in both sections with potentially different meanings. This creates ambiguity about whether system design for storage is within or outside scope.

**Recommendation**: Clarify the distinction between "storage technologies" (excluded) and "storage design considerations" (if included). Consider removing system design from scope entirely, as UIS is about information representation, not system design.

---

### STRUCTURAL ISSUES

---

**Issue S-001**

**Document**: 003 Terms and Definitions, Section 4.1 (relationship)

**Classification**: Structural

**Description**: The definition states a relationship is "A connection or association between two or more entities." "Connection" and "association" are synonymous with "relationship."

**Concern**: Circular definition. The term is defined in terms of itself.

**Recommendation**: Provide a definition that does not rely on the term itself. Consider: "A directed or undirected link between entities that expresses a meaningful connection as defined by the relationship type."

---

**Issue S-002**

**Document**: 003 Terms and Definitions, Section 3.6 (type)

**Classification**: Structural

**Description**: The term "type" is defined as "A classification that defines a category of entities with common characteristics." The term "classification" is used but not defined.

**Concern**: Reliance on an undefined related term. While "classification" is intuitive, strict terminology requires all terms to be defined or referenced.

**Recommendation**: Either define "classification" or revise to avoid the term.

---

**Issue S-003**

**Document**: 004 Design Principles, Section 2.3 (Traceability)

**Classification**: Structural

**Description**: The principle states UIS "shall enable the tracing of information to its origin," but "origin" is not defined in 003 Terms and Definitions. The term "provenance" (defined) should be used.

**Concern**: Terminology inconsistency. Traceability is described in terms of "origin" but the terms and definitions section addresses this through "provenance."

**Recommendation**: Replace "origin" with "provenance" and reference the provenance terms in 003.

---

**Issue S-004**

**Document**: 005 Architecture, Section 4.1-4.4 (Extension Points)

**Classification**: Structural

**Description**: Extension points are described inconsistently:
- 4.1 Type Extensions: "additional entity types"
- 4.3 Relationship Extensions: "additional relationship types"
- 4.4 Profile Extensions: "profiles that constrain or extend"

The distinction between "type extensions" and "relationship extensions" is unclear. Are relationship types also entity types?

**Concern**: Inconsistent categorization may lead to confusion about extension boundaries.

**Recommendation**: Establish a clear taxonomy of extensibility mechanisms and map each extension point to it.

---

**Issue S-005**

**Document**: 003 Terms and Definitions, Section 5.2 (agent)

**Classification**: Structural

**Description**: The term "agent" is defined as "An entity (person, organization, or system)." The parenthetical examples introduce concepts that may themselves require definition.

**Concern**: "Person," "organization," and "system" are domain-loaded. A "system" as an agent may imply implementation assumptions.

**Recommendation**: Provide domain-neutral examples, or define agent in terms of capability rather than entity type.

---

**Issue S-006**

**Document**: 005 Architecture, Section 6 (Specification Organization)

**Classification**: Structural

**Description**: The table lists "007-013 Core Specifications" as "Structural / Application" but does not specify which parts address which layers.

**Concern**: The table is incomplete and may mislead readers about the layering of subsequent specifications.

**Recommendation**: Expand the table to indicate the layer(s) each part addresses, or provide a reference to a detailed mapping document.

---

### EDITORIAL ISSUES

---

**Issue E-001**

**Document**: 001 Scope, Section 3.c

**Classification**: Editorial

**Description**: States UIS shall "Establish principles for structuring information," but 004 Design Principles states UIS shall not "prescribe specific file formats or encoding schemes."

**Concern**: "Structuring" may be confused with "encoding." While structurally neutral, the wording is imprecise.

**Recommendation**: Consider "Establish principles for organizing information" to avoid the structural/encoding ambiguity.

---

**Issue E-002**

**Document**: 003 Terms and Definitions, Section 2.2 (representation)

**Classification**: Editorial

**Description**: "A concrete form or encoding of information suitable for communication, processing, or storage."

**Concern**: "Concrete form" is somewhat vague. The note says "physical manifestation" which is more concrete but not stated in the definition itself.

**Recommendation**: Align the definition with the note: "A concrete manifestation of information in a specific format, suitable for communication, processing, or storage."

---

**Issue E-003**

**Document**: 003 Terms and Definitions, Section 2.4 (interoperability)

**Classification**: Editorial

**Description**: "The ability of two or more representations to exchange information and use the exchanged information."

**Concern**: "Exchange" implies bilateral communication, which may be too narrow (information can flow in one direction) and may imply transport mechanisms.

**Recommendation**: Consider: "The ability of representations to be understood and used by other representations, regardless of their origin or implementation."

---

**Issue E-004**

**Document**: 003 Terms and Definitions, Section 3.3 (information object)

**Classification**: Editorial

**Description**: An information object is "a discrete unit of structured information." This implies all information objects are necessarily structured, but unstructured information may exist.

**Concern**: The definition may exclude valid use cases where structured information objects contain unstructured components.

**Recommendation**: Consider: "A discrete unit of information with defined identity, which may be structured or unstructured, and which can be characterized by properties and relationships."

---

**Issue E-005**

**Document**: 004 Design Principles, Section 3.3 (Composability)

**Classification**: Editorial

**Description**: States UIS "should enable the construction of complex information structures from simpler components."

**Concern**: "Components" is a term with software/engineering connotations. While intuitive, it may suggest implementation approaches.

**Recommendation**: Consider: "UIS should enable the construction of complex information structures from simpler constituent elements."

---

## Summary by Document

### 001 Scope
| Issue | Classification | Priority |
|-------|---------------|----------|
| N-007 | Normative | High |
| E-001 | Editorial | Low |

### 003 Terms and Definitions
| Issue | Classification | Priority |
|-------|---------------|----------|
| N-005 | Normative | High |
| N-006 | Normative | High |
| S-001 | Structural | Medium |
| S-002 | Structural | Medium |
| S-003 | Structural | Medium |
| S-005 | Structural | Medium |
| E-002 | Editorial | Low |
| E-003 | Editorial | Low |
| E-004 | Editorial | Low |

### 004 Design Principles
| Issue | Classification | Priority |
|-------|---------------|----------|
| N-003 | Normative | High |
| N-004 | Normative | High |
| S-003 | Structural | Medium |
| E-005 | Editorial | Low |

### 005 Architecture
| Issue | Classification | Priority |
|-------|---------------|----------|
| N-001 | Normative | High |
| N-002 | Normative | High |
| S-004 | Structural | Medium |
| S-006 | Structural | Medium |

---

## Recommendations

### Immediate Actions (Before Next Draft)

1. Resolve all Normative issues (N-001 through N-007)
2. Resolve all Structural issues related to terminology (S-001, S-002, S-003)
3. Ensure consistency between 001 Scope and 004/005 on encoding-related statements

### Deferred Actions (Future Drafts)

1. Address remaining Structural issues (S-004, S-005, S-006)
2. Apply Editorial corrections for improved clarity

### Cross-Document Actions

1. Establish a terminology cross-reference index to prevent undefined term usage
2. Create a consistency checklist for future reviews

---

## Review Committee Notes

The documents demonstrate strong adherence to international standards conventions and achieve domain neutrality in most respects. The identified issues are primarily related to the tension between defining an abstract framework and avoiding implementation assumptions.

The Representation Layer contradiction (N-001) is the most critical issue and should be resolved before advancing the Architecture document to Working Draft status.

---

*This review was conducted as part of the UIS Working Draft 0.3.0 development process.*
