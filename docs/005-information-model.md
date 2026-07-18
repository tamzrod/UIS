# Information Model

## 5.1 Overview

The UIS Information Model provides an abstract representation of information that is independent of any specific implementation technology. This model establishes the foundational concepts that all conforming representations must support.

The information model is designed to be:

- **Abstract**: Independent of concrete representations
- **Complete**: Capable of describing all aspects of information
- **Consistent**: Internally coherent and well-defined
- **Extensible**: Capable of accommodating specialized requirements

## 5.2 Fundamental Concepts

### 5.2.1 Information Objects

The primary entity in the information model is the **information object**. An information object is a discrete unit of structured information that possesses identity and can be distinctly identified.

An information object:

a) Has a unique identity within its context of use

b) Has properties that describe its characteristics

c) Can have relationships with other information objects

d) Exists within a specific version

e) Has provenance describing its origin and history

### 5.2.2 Properties

Properties are the means by which information objects are characterized. A property consists of:

a) A **name** that identifies the property within its context

b) A **value** that represents the property's content

c) Optional **constraints** that restrict allowable values

Property values may be:

- **Atomic**: Simple, indivisible values (e.g., strings, numbers, dates)
- **Structured**: Complex values composed of multiple components
- **References**: Values that point to other information objects

### 5.2.3 Identifiers

Every information object shall have one or more identifiers that uniquely distinguish it. An identifier:

a) Is unique within a given identification context

b) Persists across versions of the information object

c) May be assigned by the creating system or externally

d) Shall not be reused for different information objects

## 5.3 Information Object Structure

### 5.3.1 Required Characteristics

Every information object shall possess the following characteristics:

| Characteristic | Description |
|----------------|-------------|
| Identity | A unique identifier |
| Type | Classification of the object |
| Properties | Set of properties describing the object |
| Relationships | Set of relationships to other objects |
| Provenance | Information about origin and history |

### 5.3.2 Type System

Information objects are classified by type. A type defines:

a) The properties that instances of that type must or may possess

b) Constraints on property values

c) Constraints on relationships

d) Semantics that distinguish the type from other types

Types may form hierarchies where subtypes inherit characteristics from their parent types while adding or constraining specific aspects.

### 5.3.3 Property Constraints

Properties may have constraints including:

- **Cardinality**: Minimum and maximum occurrences
- **Value type**: The kind of values permitted
- **Value constraints**: Restrictions on permitted values
- **Mandatory/optional**: Whether the property must be present

## 5.4 Information Object Lifecycle

Information objects exist in a lifecycle that includes:

1. **Creation**: The object comes into existence
2. **Versioning**: Changes result in new versions
3. **Relationship**: The object becomes connected to other objects
4. **Deactivation**: The object is no longer current but may remain accessible
5. **Deletion**: The object is removed from active use

The lifecycle does not mandate any particular storage, transmission, or processing mechanisms.

## 5.5 Model Constraints

The information model imposes the following constraints:

a) An information object cannot reference itself directly or through a cycle of relationships that would create logical inconsistency.

b) The properties of an information object shall be sufficient to determine its type.

c) Identifiers shall be stable across versions unless explicitly changed.

d) Provenance information shall be immutable for any given version.

## 5.6 Extensibility

The information model may be extended through:

a) **Profiles**: Constrained subsets for specific domains or use cases

b) **Extensions**: Additional types and properties for specialized requirements

c) **Vocabulary**: Defined sets of permitted values for constrained properties

Extensions shall not contradict or override mandatory aspects of the base model.

---

*This clause establishes the abstract information model. Subsequent clauses elaborate on specific aspects including information objects, relationships, provenance, evidence, and versioning.*
