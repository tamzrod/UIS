# DISCUSSION-0002: Scope of UIS — What Does UIS Actually Standardize?

**Discussion Number**: 0002
**Title**: Evaluating Candidate Scopes for UIS
**Status**: Exploratory
**Date**: 2026-07-18
**Author**: UIS Working Group
**Related**: DISCUSSION-0001 (Information Concepts)

---

## 1. Introduction

This document evaluates what the Universal Information Standard (UIS) actually standardizes. The current specification uses the term "information" but does not define its scope precisely. This ambiguity could lead to inconsistent interpretations and implementations.

Six candidate scopes are evaluated:

1. Information
2. Knowledge
3. Representations
4. Assertions
5. Evidence
6. Information Systems

For each candidate, this document examines:
- What is standardized
- What is outside scope
- Advantages
- Disadvantages
- Impact on the rest of the specification

The goal is to surface architectural decisions rather than select a preferred option.

---

## 2. Candidate Scope Evaluation

### 2.1 Information

**What is standardized**: The abstract concept of information as meaningful data. Information is treated as a primary entity that can be represented, communicated, and processed.

**In Scope**:
- Information objects
- Information properties and values
- Information relationships
- Information structure and organization
- Information provenance

**Outside Scope**:
- The truth of information (separate from evidence)
- Human interpretation or understanding
- Knowledge processes (learning, reasoning)
- Physical encoding formats

**Advantages**:
- Broad applicability across domains
- Aligns with intuitive understanding of "information"
- Familiar terminology (information science, information systems)
- Can address data and documents as special cases

**Disadvantages**:
- "Information" is notoriously ambiguous (see DISCUSSION-0001)
- Requires resolving the syntactic/semantic debate
- May overlap with but not fully cover other candidates
- Truth requirement unclear

**Impact on Rest of Specification**:
- **Terms and Definitions**: Requires careful definition of "information" and related terms
- **Information Model**: Central document defining information structure
- **Identity**: Information objects need identification
- **Evidence**: Evidence relates to information truth/quality
- **Conformance**: Conformance applies to information representations

---

### 2.2 Knowledge

**What is standardized**: Knowledge as structured information that has been justified, internalized, or otherwise elevated beyond mere information.

**In Scope**:
- Knowledge representations
- Knowledge structures (ontologies, taxonomies)
- Knowledge relationships
- Knowledge provenance and justification
- Knowledge systems interfaces

**Outside Scope**:
- Actual human knowledge (cognitive processes)
- Learning or reasoning mechanisms
- Belief states of agents
- Truth of knowledge claims

**Advantages**:
- Addresses higher-order information needs
- Aligns with AI/knowledge representation traditions
- Enables reasoning about knowledge quality
- Natural fit for ontology and semantics

**Disadvantages**:
- Requires defining knowledge vs. information boundary
- Potentially excludes raw data and simple facts
- May be too abstract for practical applications
- Truth and justification requirements complex

**Impact on Rest of Specification**:
- **Terms and Definitions**: Requires defining knowledge and related epistemic concepts
- **Information Model**: Knowledge structures as primary entities
- **Evidence**: Justification and evidence become central
- **Identity**: Knowledge claims and their identification
- **Provenance**: Tracks justification chains

---

### 2.3 Representations

**What is standardized**: The concrete forms or encodings used to represent information. Focus is on the representation itself rather than what it represents.

**In Scope**:
- Representation structures
- Representation syntax
- Representation formats
- Encoding mechanisms
- Serialization and deserialization

**Outside Scope**:
- Abstract information (separate from its representation)
- Meaning or interpretation of representations
- Domain semantics
- Truth or quality of represented information

**Advantages**:
- Concrete and implementable
- Clear boundaries (the representation is the thing)
- Natural fit for interoperability at syntax level
- Easier to test conformance (check representation rules)

**Disadvantages**:
- Excludes abstract layer—what is being represented?
- May be too syntactic (Shannon-like)
- Limits semantic interoperability
- May conflict with "implementation independence" goal

**Impact on Rest of Specification**:
- **Terms and Definitions**: Representation as primary concept
- **Information Model**: Represents information (meta-level concern)
- **Identity**: Representations need identifiers
- **Encoding**: May need to standardize encoding requirements
- **Conformance**: Clear conformance criteria for representation rules

---

### 2.4 Assertions

**What is standardized**: Assertions as statements or claims about the world. Assertions are the units of information that can be true or false.

**In Scope**:
- Assertion structure (subject-predicate-object patterns)
- Assertion types (factual, conditional, hypothetical)
- Assertion identity
- Assertion relationships

**Outside Scope**:
- Whether assertions are true
- Beliefs about assertions
- Evidence for assertions
- The things assertions are about

**Advantages**:
- Semantic clarity (assertions are claims)
- Natural fit for knowledge representation (triples)
- Distinguishes representation from reality
- Clear truth-bearing units

**Disadvantages**:
- Excludes non-assertional information (questions, commands)
- May be too narrow for some applications
- Requires defining what constitutes a "claim"
- Truth handling may be external

**Impact on Rest of Specification**:
- **Terms and Definitions**: Assertion as core term
- **Information Model**: Assertions as primary entities
- **Evidence**: Assertions need evidence support
- **Identity**: Assertions need unique identification
- **Conformance**: Assertion structure rules

---

### 2.5 Evidence

**What is standardized**: Evidence as information that supports or substantiates assertions. The focus is on the supportive relationship between information items.

**In Scope**:
- Evidence structures
- Evidence relationships (supports, contradicts)
- Evidence provenance
- Evidence chains and graphs
- Evidence evaluation criteria

**Outside Scope**:
- The assertions evidence supports
- Truth determination
- Belief or acceptance
- Domain-specific evidence standards

**Advantages**:
- Addresses quality and trust concerns
- Natural fit for provenance tracking
- Separates representation from truth claims
- Enables assessment without requiring truth

**Disadvantages**:
- Derivative concept—what is being evidenced?
- May be too narrow for general information
- Evidence relationships complex and domain-dependent
- May require domain-specific evidence standards

**Impact on Rest of Specification**:
- **Terms and Definitions**: Evidence as core term
- **Information Model**: Evidence relationships central
- **Assertions**: Evidence supports assertions
- **Provenance**: Evidence has its own provenance
- **Conformance**: Evidence structure rules

---

### 2.6 Information Systems

**What is standardized**: The interfaces and behaviors of information systems that create, process, store, or transmit information.

**In Scope**:
- System interfaces and APIs
- System behaviors
- Information flows
- System interoperability
- System requirements

**Outside Scope**:
- Internal system implementation
- Information structure (separate concern)
- Domain semantics
- Physical infrastructure

**Advantages**:
- Addresses practical interoperability
- Clear stakeholder benefits (systems work together)
- Natural for technology standards
- Can reference information standards

**Disadvantages**:
- Technology-dependent (conflicts with implementation independence)
- Changes with technology evolution
- May be too operational for abstract standard
- Overlaps significantly with existing API standards

**Impact on Rest of Specification**:
- **Terms and Definitions**: System and interface terminology
- **Information Model**: Information exchanged by systems
- **Representations**: Encodings used by systems
- **Identity**: System and interface identifiers
- **Conformance**: System behavior requirements

---

## 3. Comparative Analysis

### 3.1 Scope Boundaries

| Candidate | Primary Focus | Adjacent Concerns | Boundary Issues |
|-----------|--------------|-------------------|-----------------|
| Information | Meaningful data | Truth, encoding | What makes information meaningful? |
| Knowledge | Justified belief | Information, truth | Information vs. knowledge boundary |
| Representations | Concrete forms | Information, encoding | What is being represented? |
| Assertions | Truth-bearing claims | Evidence, truth | Non-assertional information |
| Evidence | Support relationships | Assertions, information | What is being evidenced? |
| Information Systems | System behavior | Information, interfaces | Implementation vs. interface |

### 3.2 Abstraction Level

| Candidate | Abstraction Level | Concrete/Abstract |
|-----------|------------------|------------------|
| Information | High | Abstract |
| Knowledge | Higher | Abstract |
| Representations | Low | Concrete |
| Assertions | Medium-High | Semi-Abstract |
| Evidence | Medium | Semi-Abstract |
| Information Systems | Low | Concrete |

### 3.3 Truth Handling

| Candidate | Truth Treatment | Implications |
|-----------|----------------|--------------|
| Information | Ambiguous | May or may not require truth |
| Knowledge | Required (justified) | Truth essential to concept |
| Representations | Irrelevant | Syntax only |
| Assertions | Central | Assertions are true or false |
| Evidence | External | Evidence relates to truth but doesn't determine it |
| Information Systems | Irrelevant | Systems don't make truth claims |

### 3.4 Interoperability Focus

| Candidate | Interoperability Aspect | Level |
|-----------|------------------------|-------|
| Information | Conceptual alignment | Semantic |
| Knowledge | Ontology mapping | Semantic |
| Representations | Format conversion | Syntactic |
| Assertions | Meaning agreement | Semantic |
| Evidence | Evidence chain linking | Organizational |
| Information Systems | Interface compliance | Technical |

---

## 4. Relationships Between Candidates

The six candidates are not independent. They have natural relationships that may inform scope decisions:

### 4.1 Hierarchical Relationships

```
Knowledge
    ↑
    | extends
    |
Information
    ↑
    | represented by
    |
Representations
```

**Interpretation**: Knowledge extends information; representations represent information.

### 4.2 Dependency Relationships

```
Assertions ← supported by ← Evidence
    ↑                           ↑
    | about                     | about
    |                           |
Information ← exchanged by → Information Systems
```

**Interpretation**: Assertions are about information; evidence supports assertions; systems exchange information.

### 4.3 Orthogonal Concerns

Some candidates address orthogonal aspects:

- **Information** vs. **Representations**: Content vs. form
- **Assertions** vs. **Evidence**: Claims vs. support
- **Knowledge** vs. **Information Systems**: Abstract vs. concrete

---

## 5. Hybrid and Composite Options

While this document evaluates single candidates, combinations are possible:

### 5.1 Information + Evidence

UIS standardizes information and the evidence relationships between information items.

**Rationale**: Addresses both content and quality without requiring truth claims.

### 5.2 Information + Representations

UIS standardizes information and its concrete representations.

**Rationale**: Bridges abstract and concrete; addresses both what and how.

### 5.3 Assertions + Evidence

UIS standardizes assertions and the evidence that supports them.

**Rationale**: Focuses on truth-bearing units and their support structure.

### 5.4 Information + Knowledge

UIS standardizes information including its knowledge-level aspects.

**Rationale**: Adopts DIKW hierarchy; information includes knowledge.

### 5.5 Minimal Core + Extension Framework

UIS standardizes a minimal core (e.g., Information) and provides extension points for other aspects.

**Rationale**: Allows domain-specific specialization while maintaining interoperability.

---

## 6. Architectural Questions Requiring Decisions

### 6.1 Primary Scope Question

> **Q1**: What is the primary subject matter that UIS standardizes?
>
> - Information
> - Knowledge
> - Representations
> - Assertions
> - Evidence
> - Information Systems
> - A combination (specify which)

### 6.2 Abstraction Level Question

> **Q2**: What level of abstraction should UIS operate at?
>
> - Purely abstract (concepts and structures)
> - Semi-abstract (some concrete requirements)
> - Concrete (encoding requirements)

### 6.3 Truth Question

> **Q3**: How should UIS handle truth?
>
> - UIS information/assertions may be true or false (no requirement)
> - UIS requires truth for some concepts (knowledge)
> - UIS addresses evidence for truth without claiming truth
> - UIS explicitly excludes truth claims

### 6.4 Scope Hierarchy Question

> **Q4**: Should UIS adopt a hierarchical structure (e.g., DIKW)?
>
> - Yes, adopt DIKW hierarchy
> - Yes, adopt a different hierarchy
> - No, treat all concepts as orthogonal
> - Defer hierarchy to future versions

### 6.5 Interoperability Focus Question

> **Q5**: What aspect of interoperability does UIS primarily address?
>
> - Syntactic interoperability (representation formats)
> - Semantic interoperability (meaning alignment)
> - Organizational interoperability (process alignment)
> - All of the above
> - Depends on domain

### 6.6 Extension Mechanism Question

> **Q6**: Should UIS define a primary scope with extension mechanisms?
>
> - Yes, define a minimal core with extension points
> - No, define a comprehensive scope
> - Define multiple profiles for different use cases

### 6.7 Domain Coverage Question

> **Q7**: Should UIS scope be universal or modular?
>
> - Universal: One scope fits all domains
> - Modular: Domain-specific scope modules
> - Hybrid: Core universal scope + domain modules

---

## 7. Summary Comparison Table

| Criterion | Information | Knowledge | Representations | Assertions | Evidence | Info Systems |
|-----------|-------------|-----------|-----------------|------------|----------|--------------|
| **Abstraction** | High | Higher | Low | Medium | Medium | Low |
| **Truth Handling** | Ambiguous | Required | Irrelevant | Central | External | Irrelevant |
| **Domain Neutrality** | High | Medium | High | High | Medium | Low |
| **Implementation Risk** | Medium | High | Low | Medium | High | Low |
| **Interoperability** | Semantic | Semantic | Syntactic | Semantic | Organizational | Technical |
| **Conceptual Clarity** | Low | Medium | High | High | Medium | High |
| **Scope Clarity** | Low | Medium | High | Medium | Medium | High |

---

## 8. Conclusion

This document has evaluated six candidate scopes for UIS. Each has distinct advantages and disadvantages:

- **Information**: Broad but ambiguous
- **Knowledge**: Rich but demanding
- **Representations**: Clear but potentially shallow
- **Assertions**: Semantic but potentially narrow
- **Evidence**: Quality-focused but derivative
- **Information Systems**: Practical but technology-dependent

The choice of scope has profound implications for the entire specification, affecting terminology, information model, conformance requirements, and interoperability capabilities.

The architectural questions in Section 6 must be resolved before the specification scope can be finalized.

---

## 9. References

1. UIS. (2026). *Scope*. Working Draft 0.3.0. `docs/001-scope.md`

2. UIS. (2026). *What is Information?* Discussion 0001. `docs/DISCUSSION-0001-information.md`

3. Shannon, C. E. (1948). *A Mathematical Theory of Communication*. Bell System Technical Journal.

4. Floridi, L. (2004). *Semantic Conceptions of Information*. Stanford Encyclopedia of Philosophy.

5. Davis, R., Shrobe, H., & Szolovits, P. (1993). *What Is a Knowledge Representation?* AI Magazine.

6. Ackoff, R. L. (1989). *From Data to Wisdom*. Journal of Applied Systems Analysis.

---

*This is a discussion document for UIS Working Draft development. It does not constitute normative specification content.*
