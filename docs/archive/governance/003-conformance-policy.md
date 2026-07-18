# Conformance Policy

## 1. General

This document defines the policies and procedures for conformance to the Universal Information Standard (UIS). The conformance policy is designed to support self-assessment models suitable for single-author development while providing frameworks for formal certification when appropriate.

## 2. Conformance Levels

UIS defines two levels of conformance:

### 2.1 Full Conformance

A representation achieves Full Conformance when it satisfies all mandatory requirements of UIS.

**Requirements**:
- All SHALL requirements are satisfied
- All SHALL NOT requirements are not violated
- All normative definitions are implemented as specified

### 2.2 Partial Conformance

A representation achieves Partial Conformance when it satisfies some but not all mandatory requirements.

**Requirements**:
- Mandatory requirements that are satisfied are implemented correctly
- Non-conformant aspects are documented
- Conformance claims specify which requirements are not satisfied

## 3. Conformance Claims

### 3.1 Self-Assessment

Implementations may claim conformance through self-assessment:

- Implementer evaluates their representation against UIS requirements
- No external verification is required
- Claim is made at implementer's discretion and responsibility

### 3.2 Verified Conformance

Implementations may seek verified conformance:

- Third-party assessment of conformance
- May be required by domain-specific profiles
- Certificate or verification statement issued

### 3.3 Claim Documentation

Conformance claims should document:

- Version of UIS to which conformance is claimed
- Level of conformance (Full or Partial)
- Any optional features implemented
- Any known limitations or deviations

## 4. Conformance Requirements

### 4.1 Representations

A conforming representation SHALL:

- Satisfy all applicable mandatory requirements
- Provide accurate conformance claim documentation
- Identify any implemented extensions

### 4.2 Extensions

Extensions to UIS SHALL:

- Not contradict mandatory UIS requirements
- Be clearly identified as extensions to UIS
- Not be claimed as UIS conformance unless full conformance is achieved

### 4.3 Profiles

Domain-specific profiles MAY define additional requirements. Conformance to a profile requires:

- Full Conformance to UIS, plus
- Satisfaction of all profile-specific requirements

## 5. Conformance Testing

### 5.1 Test Philosophy

UIS does not mandate specific conformance tests. However:

- Implementations SHOULD verify their conformance before claiming it
- Testing methodologies are encouraged but not required
- Self-assessment is sufficient for conformance claims

### 5.2 Test Documentation

When conformance tests are used:

- Test methodology may be documented
- Test results may be published
- Neither is required for conformance claims

## 6. Applicability by Governance Model

### 6.1 Single Author

In single-author development:

- Self-assessment is the primary conformance mechanism
- Formal certification is optional
- Author documents conformance of their implementation

### 6.2 Open Community

In open community development:

- Self-assessment remains valid
- Community may develop shared testing tools
- Verification services may emerge voluntarily

### 6.3 Formal Organization

In formal organization development:

- Verified conformance may be required
- Certification bodies may be designated
- Testing laboratories may be accredited

## 7. Conformance Marks

### 7.1 Usage

Implementations may use conformance marks to indicate their conformance status:

- "UIS Conformant" indicates Full Conformance
- "UIS Partial" indicates Partial Conformance
- Marks should reference the UIS version

### 7.2 Restrictions

Conformance marks SHALL NOT be used:

- To indicate endorsement by UIS project
- To imply official certification without verification
- In ways that could confuse users about conformance status

## 8. Dispute Resolution

### 8.1 Conformance Disputes

Disputes about conformance claims are resolved through:

1. Documentation review
2. Technical assessment
3. Community deliberation

### 8.2 Remedies

Possible remedies for non-conformance include:

- Clarification of conformance requirements
- Correction of conformance claims
- Withdrawal of invalid conformance claims

## 9. Review and Amendment

This conformance policy may be amended via Architectural Decision process.
