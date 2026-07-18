# ADR-0001: UIS Scope Definition

**ADR Number**: 0001
**Title**: Determining the Scope of UIS
**Status**: **Proposed**
**Date**: 2026-07-18
**Author**: UIS Working Group
**Related**:
- DISCUSSION-0001: What is Information?
- DISCUSSION-0002: Scope of UIS
- ADL-0.3.0: DECISION-001 through DECISION-006

---

## 1. Status

**Proposed**

This ADR is submitted for Architectural Decision review. The recommendation section contains an analysis rather than a proposed decision, pending further deliberation.

---

## 2. Context

### 2.1 Problem Statement

UIS is defined as a "universal framework for representing information." However, the term "information" is ambiguous across disciplines, and the actual scope of UIS has not been precisely defined. This ambiguity creates several risks:

1. **Inconsistent implementations**: Implementations may interpret "information" differently, reducing interoperability
2. **Scope creep**: Without clear boundaries, UIS may expand to cover areas better addressed by other standards
3. **Unresolved debates**: Fundamental questions (syntactic vs. semantic, truth requirements, agent-dependence) remain unresolved
4. **Conformance ambiguity**: Without clear scope, conformance testing is difficult

### 2.2 Evidence Gathered

The following discussion documents provide evidence for this decision:

**DISCUSSION-0001: What is Information?**
- Surveyed 6 perspectives: Shannon theory, semantic information, epistemology, knowledge representation, systems engineering, library science
- Identified 5 major conflicts: syntactic/semantic, objective/subjective, truth requirement, agent-dependence, data/information distinction
- Identified 7 universal concepts: entity, property, value, relationship, type/category, identifier, representation
- Established 7 open questions for architectural decisions

**DISCUSSION-0002: Scope of UIS**
- Evaluated 6 candidate scopes: Information, Knowledge, Representations, Assertions, Evidence, Information Systems
- Analyzed each candidate across 7 criteria
- Identified relationships between candidates (hierarchical, dependency, orthogonal)
- Proposed 5 hybrid/composite options
- Established 7 architectural questions requiring decisions

### 2.3 Scope of This Decision

This ADR addresses the foundational scope question:

> **What is the primary subject matter that UIS standardizes?**

This decision will influence:
- Terminology definitions (Terms and Definitions)
- Information Model structure
- Extension mechanisms
- Conformance requirements
- Interoperability guarantees

This decision does NOT address:
- Specific encoding requirements (Encoding Scope, DECISION-001)
- Profile normative status (DECISION-002)
- Specific terminology definitions (will follow after scope decision)
- Extension taxonomy (DECISION-008)

---

## 3. Alternatives Considered

### 3.1 Information (Primary Scope)

**Description**: UIS standardizes information as meaningful, structured data.

**Position**: The current specification language implies this scope.

**Evidence For**:
- Aligns with current specification language ("representing information")
- Familiar terminology for broad audience
- Survey evidence shows "information" has universal characteristics (structured, relational, processable, contextual)
- Candidates for UIS primitives identified (entity, property, relationship, value)

**Evidence Against**:
- "Information" is notoriously ambiguous (see DISCUSSION-0001)
- Requires resolving syntactic/semantic debate
- Truth handling unclear
- May be too broad or too narrow depending on interpretation

### 3.2 Knowledge (Primary Scope)

**Description**: UIS standardizes knowledge as justified, structured information.

**Evidence For**:
- Addresses higher-order information needs
- Natural fit for AI/knowledge representation traditions
- Truth requirement addresses quality concerns
- Enables reasoning about knowledge quality

**Evidence Against**:
- Requires defining knowledge vs. information boundary
- May exclude raw data and simple facts
- Justification requirements add complexity
- Truth requirements may be too demanding

### 3.3 Representations (Primary Scope)

**Description**: UIS standardizes the concrete forms or encodings used to represent information.

**Evidence For**:
- Concrete and implementable
- Clear boundaries
- Natural for syntactic interoperability
- Easier conformance testing

**Evidence Against**:
- May be too syntactic (Shannon-like)
- Excludes abstract layer
- Limits semantic interoperability
- May conflict with "implementation independence" goal

### 3.4 Assertions (Primary Scope)

**Description**: UIS standardizes assertions as truth-bearing statements.

**Evidence For**:
- Semantic clarity
- Natural fit for knowledge representation (triples)
- Clear truth-bearing units
- Distinguishes representation from reality

**Evidence Against**:
- Excludes non-assertional information (questions, commands)
- May be too narrow for some applications
- Requires defining what constitutes a "claim"
- Truth handling complex

### 3.5 Evidence (Primary Scope)

**Description**: UIS standardizes evidence as information that supports assertions.

**Evidence For**:
- Addresses quality and trust concerns
- Natural for provenance tracking
- Separates representation from truth claims
- Enables assessment without requiring truth

**Evidence Against**:
- Derivative concept—what is being evidenced?
- May be too narrow for general information
- Evidence relationships complex
- May require domain-specific standards

### 3.6 Information Systems (Primary Scope)

**Description**: UIS standardizes information system interfaces and behaviors.

**Evidence For**:
- Addresses practical interoperability
- Clear stakeholder benefits
- Natural for technology standards
- Implementation guidance

**Evidence Against**:
- Technology-dependent
- Changes with technology evolution
- May be too operational
- Overlaps with existing API standards

### 3.7 Hybrid Approaches

**Description**: Combinations of the above as primary scope.

**3.7.1 Information + Evidence**

UIS standardizes information and the evidence relationships between information items.

**Rationale**: Addresses both content and quality without requiring truth claims.

**3.7.2 Information + Representations**

UIS standardizes information and its concrete representations.

**Rationale**: Bridges abstract and concrete; addresses both what and how.

**3.7.3 Assertions + Evidence**

UIS standardizes assertions and the evidence that supports them.

**Rationale**: Focuses on truth-bearing units and their support structure.

**3.7.4 Minimal Core + Extension Framework**

UIS standardizes a minimal core (Information) with defined extension points for other aspects.

**Rationale**: Allows domain-specific specialization while maintaining interoperability.

---

## 4. Evaluation Criteria

Each alternative is evaluated against the following criteria, derived from UIS Design Principles:

### 4.1 Domain Neutrality

The ability for UIS to apply across all domains without favoring any particular field.

| Alternative | Assessment | Rationale |
|-------------|------------|-----------|
| Information | Medium | Broad appeal but ambiguous definition |
| Knowledge | Lower | Requires justification mechanisms |
| Representations | Higher | Format-focused, domain-neutral |
| Assertions | Medium | Semantic but potentially narrow |
| Evidence | Medium | Support-focused but domain-variable |
| Information Systems | Lower | Technology-focused, domain-variable |
| Hybrid (I+E) | Medium-High | Balances content and quality |

### 4.2 Simplicity

The degree to which the scope is understandable and implementable.

| Alternative | Assessment | Rationale |
|-------------|------------|-----------|
| Information | Lower | Ambiguous definition requires clarification |
| Knowledge | Lower | Justification requirements add complexity |
| Representations | Higher | Concrete, format-focused |
| Assertions | Medium | Structured but requires semantics |
| Evidence | Medium | Support relationships can be complex |
| Information Systems | Higher | Interfaces are concrete |
| Hybrid (I+E) | Medium | Two concepts but complementary |

### 4.3 Interoperability

The ability to enable exchange between different systems.

| Alternative | Assessment | Rationale |
|-------------|------------|-----------|
| Information | Medium | Semantic interoperability possible |
| Knowledge | Medium | Semantic, but knowledge definitions vary |
| Representations | Higher | Syntactic interoperability clear |
| Assertions | Medium | Semantic alignment required |
| Evidence | Lower-Medium | Organizational interoperability |
| Information Systems | Higher | Interface compliance |
| Hybrid (I+E) | Medium | Both levels possible |

### 4.4 Longevity

The stability of the scope over time.

| Alternative | Assessment | Rationale |
|-------------|------------|-----------|
| Information | Higher | Core concept, unlikely to become obsolete |
| Knowledge | Medium | Justification concepts may evolve |
| Representations | Lower | Encoding formats change |
| Assertions | Higher | Semantic units stable |
| Evidence | Higher | Support relationships timeless |
| Information Systems | Lower | Technology-dependent |
| Hybrid (I+E) | Medium-High | Core concepts stable |

### 4.5 Extensibility

The ability to accommodate domain-specific requirements.

| Alternative | Assessment | Rationale |
|-------------|------------|-----------|
| Information | Higher | Universal concept with extensions |
| Knowledge | Medium | Extensions require justification context |
| Representations | Lower | Format extensions limited |
| Assertions | Medium | Assertion types can be extended |
| Evidence | Medium | Evidence types domain-variable |
| Information Systems | Higher | Interface extensions natural |
| Hybrid (I+E) | Medium-High | Information extensible, evidence adds structure |

### 4.6 Implementation Independence

Freedom from specific technologies or platforms.

| Alternative | Assessment | Rationale |
|-------------|------------|-----------|
| Information | Higher | Abstract concept, technology-neutral |
| Knowledge | Higher | Abstract concept, technology-neutral |
| Representations | Lower | Requires specific format |
| Assertions | Higher | Abstract semantic units |
| Evidence | Higher | Abstract support relationships |
| Information Systems | Lower | Requires specific interfaces |
| Hybrid (I+E) | Higher | Both abstract concepts |

### 4.7 Evaluation Summary

| Alternative | Domain Neutrality | Simplicity | Interoperability | Longevity | Extensibility | Impl. Independence | **Total** |
|-------------|------------------|------------|-----------------|-----------|---------------|-------------------|----------|
| Information | M | L | M | H | H | H | **15** |
| Knowledge | L | L | M | M | M | H | **13** |
| Representations | H | H | H | L | L | L | **13** |
| Assertions | M | M | M | H | M | H | **15** |
| Evidence | M | M | L-M | H | M | H | **14** |
| Information Systems | L | H | H | L | H | L | **12** |
| Hybrid (I+E) | M-H | M | M | M-H | M-H | H | **15-16** |

*Scale: H=3, M=2, L=1*

---

## 5. Consequences

### 5.1 If Information is Selected

**Positive**:
- Aligns with current specification language
- Broad applicability maintained
- Core concepts (entity, property, relationship) enable extensibility

**Negative**:
- Requires resolving information definition ambiguity
- Truth handling must be decided
- May be perceived as too broad

**Specification Impact**:
- Terms and Definitions requires careful "information" definition
- Information Model central to specification
- Evidence/Assertions may become extensions

### 5.2 If Knowledge is Selected

**Positive**:
- Addresses quality and justification needs
- Enables reasoning support
- Aligns with AI traditions

**Negative**:
- Adds justification requirements
- May exclude simple data representations
- Boundary with "information" requires definition

**Specification Impact**:
- New terms: justification, belief, knowledge claim
- Knowledge Model may replace Information Model
- Information becomes lower-level concept

### 5.3 If Representations is Selected

**Positive**:
- Concrete and implementable
- Clear conformance criteria
- Natural for syntactic interoperability

**Negative**:
- May be too syntactic
- Excludes semantic layer
- May overlap with existing format standards

**Specification Impact**:
- Encoding requirements become normative
- Information Model becomes meta-level
- Semantic concerns delegated elsewhere

### 5.4 If Assertions is Selected

**Positive**:
- Semantic clarity
- Truth-bearing units enable reasoning
- Natural fit for structured data

**Negative**:
- Excludes non-assertional content
- Requires semantic definitions
- Truth determination external

**Specification Impact**:
- Assertion Model central
- Information becomes "assertion content"
- Evidence becomes assertion support

### 5.5 If Evidence is Selected

**Positive**:
- Addresses quality/trust explicitly
- Separates from truth claims
- Enables provenance tracking

**Negative**:
- Derivative concept
- What is being evidenced?
- Evidence relationships complex

**Specification Impact**:
- Evidence Model central
- What is evidenced requires separate definition
- Information/Assertions become evidence subjects

### 5.6 If Information Systems is Selected

**Positive**:
- Addresses practical interoperability
- Clear implementation guidance
- Stakeholder benefits tangible

**Negative**:
- Technology-dependent
- May conflict with implementation independence
- Overlaps with existing standards

**Specification Impact**:
- Interface specifications become normative
- Information Model describes interfaces
- Technology-specific profiles needed

### 5.7 If Hybrid Approach is Selected

**Positive**:
- Addresses multiple concerns
- Can balance competing requirements
- Flexible for different use cases

**Negative**:
- More complex than single-scope
- Relationships between scopes must be defined
- Conformance may have multiple levels

**Specification Impact**:
- Multiple models may be required
- Relationship between concepts must be defined
- Extension mechanisms enable specialization

---

## 6. Recommendation

### 6.1 Analysis

Based on the evidence from DISCUSSION-0001 and DISCUSSION-0002, and the evaluation against established criteria, the following observations emerge:

1. **Information** and **Assertions** score highest on overall evaluation (15 points)
2. **Representations** excels on practicality but scores lowest on longevity and extensibility
3. **Information Systems** excels on practicality but conflicts with implementation independence
4. **Knowledge** and **Evidence** offer semantic depth but add complexity
5. **Hybrid approaches** offer flexibility but require additional definition

### 6.2 Key Considerations

**For Information**:
- The ambiguity of "information" is both a strength and weakness
- Survey evidence shows universal characteristics (structured, relational, processable, contextual)
- Core primitives (entity, property, relationship, value, type, identifier, representation) are well-supported
- Truth handling can be addressed through separate architectural decisions

**Against Information (as currently undefined)**:
- "Information" alone does not address quality/trust concerns
- Evidence and Assertions address related but distinct concerns
- A hybrid approach may better address the full range of UIS requirements

### 6.3 Recommendation: No Decision — Proposed Direction

**Recommendation**: **No Decision**

The evidence gathered is insufficient to make a final determination. However, the analysis suggests a **proposed direction** for further deliberation:

> **Proposed Direction**: UIS should adopt **Information** as its primary scope, with **Evidence** as a closely associated extension.

**Rationale for Proposed Direction**:

1. **Alignment with Current Language**: Matches existing specification references to "information"

2. **Universal Characteristics**: Survey evidence (DISCUSSION-0001) shows information has universal characteristics across disciplines

3. **Primitive Support**: Information scope supports the identified UIS primitives (entity, property, relationship, value, type, identifier, representation)

4. **Extension Mechanism**: Evidence addresses quality/trust without requiring truth claims, enabling a natural extension relationship

5. **Implementation Independence**: Both Information and Evidence are abstract concepts, supporting technology independence

6. **Scalability**: The hybrid approach (Information + Evidence) scales across governance models

### 6.4 Conditions for Advancement

Before this ADR advances to Accepted status, the following should be resolved:

1. **DECISION-001 (Encoding Scope)**: Determine whether UIS addresses encoding requirements
2. **DECISION-003 (Truth Requirement)**: Clarify whether UIS information requires truth
3. **DECISION-006 (System Scope)**: Clarify whether UIS addresses system concerns

### 6.5 Alternative Recommendation

If the committee determines that evidence is sufficient, an alternative recommendation is:

> **Alternative**: UIS should adopt a **Minimal Core + Extension Framework** approach, with Information as the core and Evidence, Assertions, and Knowledge as defined extension modules.

This approach:
- Provides maximum flexibility
- Enables domain-specific specialization
- Maintains interoperability at the core level
- Requires additional architectural decisions on extension mechanisms

---

## 7. Decision History

| Date | Status | Notes |
|------|--------|-------|
| 2026-07-18 | Proposed | Initial ADR created |

---

## 8. References

1. UIS. (2026). *Scope*. Working Draft 0.3.0. `docs/001-scope.md`

2. UIS. (2026). *What is Information?* Discussion 0001. `docs/DISCUSSION-0001-information.md`

3. UIS. (2026). *Scope of UIS*. Discussion 0002. `docs/DISCUSSION-0002-scope-of-uis.md`

4. UIS. (2026). *Architectural Decision Log*. `docs/ADL-0.3.0.md`

5. UIS. (2026). *Design Principles*. Working Draft 0.3.0. `docs/004-design-principles.md`

6. UIS. (2026). *Decision Process*. `governance/002-decision-process.md`

---

## 9. Change Log

| Version | Date | Changes |
|---------|------|---------|
| 1.0 | 2026-07-18 | Initial proposal |

---

*This ADR was created following the process defined in governance/002-decision-process.md*
