# Relationships

## 8.1 Overview

Relationships connect information objects and other entities within the UIS framework. This clause defines the nature, types, and representation of relationships.

## 8.2 Relationship Definition

A relationship is a connection or association between two or more entities. Relationships have:

a) **Source**: The entity from which the relationship originates

b) **Target**: The entity toward which the relationship is directed

c) **Type**: The classification that defines the relationship semantics

d) **Properties**: Characteristics that describe the relationship

e) **Direction**: Optional indication of whether the relationship is directional

## 8.3 Relationship Types

### 8.3.1 Hierarchical Relationships

Relationships that establish parent-child or whole-part structures:

- **Partitive**: Establishes composition or containment
- **Specialization**: Establishes type inheritance
- **Version**: Establishes version lineage

### 8.3.2 Associative Relationships

Relationships that connect entities without establishing hierarchy:

- **Reference**: Points to related information
- **Association**: Indicates general connection
- **Equivalence**: Indicates sameness or strong similarity

### 8.3.3 Temporal Relationships

Relationships concerning time:

- **Precedence**: One entity precedes another
- **Contemporaneity**: Entities exist at the same time
- **Causality**: One entity causes another

### 8.3.4 Semantic Relationships

Relationships concerning meaning:

- **Related**: General semantic connection
- **Narrower**: More specific concept
- **Broader**: More general concept

## 8.4 Relationship Properties

Relationships may have properties including:

a) **Cardinality**: How many target entities are permitted

b) **Optionality**: Whether the relationship must exist

c) **Temporal bounds**: When the relationship is effective

d) **Strength**: Indicating relationship importance or reliability

e) **Annotation**: Additional descriptive information

## 8.5 Relationship Constraints

### 8.5.1 Structural Constraints

- An information object may participate in any number of relationships
- A relationship shall have at least one source and one target
- Circular relationships are permitted when semantically valid

### 8.5.2 Type Constraints

- The type of a relationship shall be defined
- The source and target entities shall be compatible with the relationship type
- Constraints on cardinality shall be observed

## 8.6 Relationship Navigation

UIS does not prescribe:

a) Methods for traversing relationships

b) Algorithms for relationship resolution

c) Storage structures for relationship graphs

Implementations may provide any mechanisms appropriate to their requirements.

## 8.7 Conformance

A relationship representation conforms to UIS if it:

1. Identifies the source entity or entities

2. Identifies the target entity or entities

3. Specifies the relationship type

4. Documents applicable properties

5. Observes any declared constraints

6. Supports provenance tracking for relationship creation and modification

---

*Note: The Evidence section is located in [Clause 7](007-evidence.md). This clause number reflects the planned structure and may be adjusted.*
