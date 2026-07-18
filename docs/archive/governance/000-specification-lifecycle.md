# Specification Lifecycle

## 1. General

This document defines the lifecycle stages and transitions for the Universal Information Standard (UIS). The lifecycle model is designed to accommodate both single-author development and multi-author collaboration without requiring formal committee structures.

## 2. Maturity Stages

UIS progresses through the following maturity stages:

### 2.1 Working Draft (WD)

**Description**: Initial development stage. Content is incomplete and subject to significant change.

**Characteristics**:
- All substantive content requires Architectural Decision approval
- Changes are frequent and may be breaking
- Stability is not guaranteed
- Review feedback is actively solicited

**Transition to**: Committee Draft (if multi-author) or advancement within Working Draft (if single-author)

### 2.2 Committee Draft (CD)

**Description**: Stable development stage for collaborative work. Content is reviewed but may still change.

**Characteristics**:
- Architectural Decisions require documented approval
- Changes are tracked and versioned
- Compatibility is considered but not guaranteed
- Review is systematic

**Transition to**: Proposed Standard or subsequent Committee Draft

### 2.3 Proposed Standard (PS)

**Description**: Mature specification ready for wider review and implementation testing.

**Characteristics**:
- Architectural Decisions are frozen except for essential corrections
- Changes require strong justification
- Backward compatibility is maintained when possible
- Implementations are encouraged

**Transition to**: Standard or return to Committee Draft

### 2.4 Standard (STD)

**Description**: Stable, normative specification.

**Characteristics**:
- Changes are rare and require formal process
- Backward compatibility is maintained
- Multiple implementations exist or are expected
- Conformance testing is available

**Transition to**: Superseded (by newer version) or Historic (preserved for reference)

## 3. Stage Transitions

### 3.1 Transition Requirements

| From | To | Requirement |
|------|-----|-------------|
| Working Draft | Committee Draft | Documented Architectural Decisions; stable core specification |
| Committee Draft | Proposed Standard | Successful review; implementation evidence; no blocking issues |
| Proposed Standard | Standard | Final review; interoperability demonstration; approval |

### 3.2 Transition Authority

The authority to approve transitions scales with the governance model:

| Governance Model | Transition Authority |
|------------------|----------------------|
| Single Author | Author documents decision; no external approval required |
| Open Community | Documented decision with community review period |
| Formal Organization | Committee vote per [002-decision-process.md](002-decision-process.md) |

## 4. Stability Classifications

### 4.1 Experimental

Content marked experimental has no stability guarantee. Implementations should expect breaking changes.

### 4.2 Stable

Content marked stable has passed through at least one review cycle. Breaking changes are avoided when possible.

### 4.3 Normative

Content marked normative is mandatory for conformance. Changes follow formal amendment procedures.

## 5. Maintenance Activities

### 5.1 Corrections

Corrections address errors, ambiguities, or omissions without changing substantive requirements.

**Authority**: Editor (single-author) or designated correction authority (multi-author)

### 5.2 Amendments

Amendments add, modify, or remove substantive content.

**Authority**: Architectural Decision Required (see [002-decision-process.md](002-decision-process.md))

### 5.3 Interpretations

Interpretations provide guidance on applying the specification.

**Authority**: Editor or interpretive body as defined by governance model

## 6. Applicability by Governance Model

The lifecycle applies to all governance models, with adaptations:

| Activity | Single Author | Open Community | Formal Organization |
|----------|---------------|----------------|---------------------|
| New content | Author decision | ADR with community input | Committee vote |
| Corrections | Author decision | Editor with review | Designated authority |
| Amendments | Author decision | ADR with comment period | Committee vote |
| Stage transitions | Author decision | Documented decision | Committee vote |
