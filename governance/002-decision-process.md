# Decision Process

## 1. General

This document defines the process for making decisions regarding the development and evolution of the Universal Information Standard (UIS). The decision process is designed to scale from single-author development to formal standards organizations.

## 2. Governance Roles

UIS defines four governance roles. These roles are responsibilities, not necessarily distinct individuals. In single-author development, one person may hold multiple roles.

### 2.1 Author

**Responsibility**: Creates initial content for UIS specification.

**Activities**:
- Writes specification content
- Proposes Architectural Decisions
- Documents rationale for proposals
- Responds to review feedback

**Authority**: Owns proposals until submitted for review

### 2.2 Editor

**Responsibility**: Ensures consistency, quality, and correctness of UIS specification.

**Activities**:
- Reviews proposed content for technical accuracy
- Ensures consistency with existing specification
- Maintains terminology and style guide
- Approves corrections and clarifications

**Authority**: Controls content quality and consistency; may approve or reject corrections

### 2.3 Reviewer

**Responsibility**: Evaluates proposed content and decisions.

**Activities**:
- Reviews proposed changes
- Provides feedback on correctness and completeness
- Identifies issues and concerns
- Supports or challenges proposals

**Authority**: Provides input to decisions; does not make binding decisions

### 2.4 Approver

**Responsibility**: Authorizes changes to UIS specification.

**Activities**:
- Evaluates Architectural Decisions
- Approves, rejects, or defers proposals
- Documents decision rationale
- Authorizes stage transitions

**Authority**: Makes binding decisions on specification content

### 2.5 Role Assignment by Governance Model

| Role | Single Author | Open Community | Formal Organization |
|------|--------------|----------------|---------------------|
| Author | Primary author | Contributors | Designated authors |
| Editor | Author | Appointed editor | Appointed editor |
| Reviewer | Self-review | Community | Committee members |
| Approver | Author | Author or editor | Committee or board |

## 3. Architectural Decisions

Architectural Decisions (AD) are significant decisions that affect the structure, scope, or normative content of UIS.

### 3.1 When an Architectural Decision is Required

An Architectural Decision is required when a change:

- Affects conformance requirements
- Changes normative terminology
- Introduces new architectural concepts
- Modifies existing architectural decisions
- Alters specification scope
- Affects interoperability guarantees

### 3.2 When an Architectural Decision is NOT Required

The following do not require Architectural Decisions:

- Editorial corrections (approved by Editor)
- Clarifications that do not change meaning
- Informative content additions
- Cross-reference updates
- Formatting and style changes
- Informative examples and explanations

## 4. Decision Process Flow

```
┌─────────────────────────────────────────────────────────────────┐
│                         ISSUE IDENTIFIED                        │
└─────────────────────────────────────────────────────────────────┘
                                  │
                                  ▼
┌─────────────────────────────────────────────────────────────────┐
│                    Architectural Decision Record                  │
│  - Issue statement                                              │
│  - Options considered                                           │
│  - Recommendation                                               │
│  - Affected documents                                           │
└─────────────────────────────────────────────────────────────────┘
                                  │
                                  ▼
┌─────────────────────────────────────────────────────────────────┐
│                         REVIEW PERIOD                           │
│  - Single Author: Self-review                                   │
│  - Open Community: 14-day comment period                       │
│  - Formal Org: Committee review per organizational policy       │
└─────────────────────────────────────────────────────────────────┘
                                  │
                                  ▼
┌─────────────────────────────────────────────────────────────────┐
│                          DECISION MADE                          │
└─────────────────────────────────────────────────────────────────┘
                                  │
                    ┌─────────────┼─────────────┐
                    ▼             ▼             ▼
              ┌──────────┐ ┌──────────┐ ┌──────────┐
              │ ACCEPTED │ │ REJECTED │ │ DEFERRED │
              └──────────┘ └──────────┘ └──────────┘
                    │             │             │
                    ▼             ▼             ▼
              ┌──────────┐ ┌──────────┐ ┌──────────┐
              │ Implement│ │Document  │ │ Monitor  │
              │ in Spec │ │ Rationale│ │ for Future│
              └──────────┘ └──────────┘ └──────────┘
```

## 5. Decision Outcomes

### 5.1 Accepted

The Architectural Decision is approved for implementation.

**Actions**:
- Update specification per decision
- Document in CHANGELOG
- Reference in Architectural Decision Log

### 5.2 Rejected

The proposed change is not approved.

**Actions**:
- Document rationale for rejection
- Proposal may be revised and resubmitted
- Record in Architectural Decision Log

### 5.3 Deferred

The decision is postponed to a future version or review cycle.

**Actions**:
- Document reason for deferral
- Note conditions for reconsideration
- Track in Deferred Decisions register

## 6. Decision Criteria

Decisions should consider:

a) **Correctness**: Does the proposal accurately solve the identified issue?

b) **Consistency**: Is the proposal consistent with existing UIS architecture?

c) **Completeness**: Does the proposal address all aspects of the issue?

d) **Impact**: What is the effect on existing implementations and conformance?

e) **Reversibility**: Can the decision be reversed if proven incorrect?

f) **Alignment**: Does the proposal align with UIS Design Principles?

## 7. Documentation Requirements

### 7.1 Architectural Decision Record (ADR)

Each Architectural Decision shall document:

- **Title**: Clear, concise description
- **Issue**: Problem or opportunity being addressed
- **Decision**: What was decided
- **Options**: Alternatives that were considered
- **Rationale**: Why this decision was made
- **Consequences**: Positive and negative effects
- **Affected Documents**: UIS documents impacted
- **Status**: Accepted, Rejected, or Deferred
- **Date**: When decision was made

### 7.2 Architectural Decision Log

All Architectural Decisions are recorded in the Architectural Decision Log (ADL), located in `docs/ADL-<version>.md`.

## 8. Scalability

### 8.1 Single Author Model

In single-author development:

- Author creates and reviews proposals
- Author makes and implements decisions
- All decisions are documented in ADL
- Process provides structure without external requirements

### 8.2 Open Community Model

In open community development:

- Contributors submit proposals via issues or pull requests
- Community review period allows for input
- Editor manages review process
- Approver (Author or Editor) makes final decisions
- Transparent documentation maintains trust

### 8.3 Formal Organization Model

In formal organization development:

- Committee members have defined roles
- Voting procedures per organizational rules
- Quorum and majority thresholds apply
- Decisions are binding on all participants
- Appeals process available per organizational policy

## 9. Exceptions

### 9.1 Emergency Corrections

Errors that could cause harm or significant confusion may be corrected without full Architectural Decision process, subject to:

- Immediate notification to affected parties
- Documentation of the correction and rationale
- Review at next available opportunity

### 9.2 Experimental Features

New features may be marked experimental, allowing:

- Implementation without full Architectural Decision
- Feedback collection before final decision
- Removal without backward compatibility concern

## 10. Review and Amendment

This governance document may be amended via Architectural Decision process.
