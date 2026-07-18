# Versioning

## 10.1 Overview

Versioning addresses the management of information change over time. This clause defines concepts and requirements for representing versions and managing information evolution.

## 10.2 Version Definition

A version is a specific state of an information object at a point in time. Versions capture:

a) The structure and content of the information object

b) The point in time the state was established

c) The relationship to previous and subsequent versions

## 10.3 Version Identifiers

Each version shall have a unique identifier within its information object's history.

### 10.3.1 Identifier Characteristics

Version identifiers shall:

- Be unique within the information object's version history
- Be assigned when the version is created
- Not be reused for other versions
- Persist as the permanent designation of that version

### 10.3.2 Identifier Schemes

UIS does not prescribe a specific identifier scheme. Schemes may include:

- Sequential numbers (1, 2, 3...)
- Timestamps (2024-01-15T10:30:00Z)
- Semantic versions (1.0.0, 1.1.0, 2.0.0)
- UUIDs or other unique strings

## 10.4 Version Relationships

Versions form a history through relationships:

a) **Successor**: Links to the subsequent version

b) **Predecessor**: Links to the previous version

c) **Branch**: Links to a divergent version

d) **Merge**: Links versions that have been combined

## 10.5 Version Types

### 10.5.1 Sequential Versions

Versions that follow one another in a linear history:

- Version 1 → Version 2 → Version 3

### 10.5.2 Branch Versions

Versions that diverge from an existing line:

- Version 1 → Version 2 → Version 3a
                         → Version 3b

### 10.5.3 Merge Versions

Versions that combine content from multiple sources:

- Version 3a → Version 3ab ← Version 3b

## 10.6 Change Description

Versions may document:

a) **Change type**: The nature of modifications

b) **Change description**: Explanation of what changed

c) **Change rationale**: Why the change was made

d) **Changed by**: Agent responsible for the change

e) **Changed when**: Timestamp of the change

## 10.7 Change Types

Common change types include:

| Type | Description |
|------|-------------|
| Creation | Initial version of a new information object |
| Correction | Fixing errors in previous versions |
| Update | Adding or modifying content |
| Revision | Significant restructuring |
| Deletion | Marking information as removed |

## 10.8 Version Constraints

The following constraints apply:

a) Every information object shall have at least one version

b) The initial version shall be designated as such

c) Subsequent versions shall reference their predecessor

d) Version identifiers shall not change once assigned

## 10.9 Conformance

A versioning representation conforms to UIS if it:

1. Assigns a unique identifier to each version

2. Establishes relationships between related versions

3. Documents the type of change represented

4. Records when the version was created

5. Indicates which version is current or canonical

6. Maintains the immutability of historical versions

## 10.10 Versioning Policies

UIS does not mandate specific versioning policies. Organizations may establish policies concerning:

- Version naming conventions
- Change approval requirements
- Version retention periods
- Branch and merge practices

Such policies are outside the scope of this specification.
