# Information Objects

## 6.1 Overview

This clause defines the concept of information objects within the UIS framework. Information objects are the fundamental units of structured information that the specification addresses.

## 6.2 Information Object Definition

An information object is a discrete, identifiable unit of information that:

a) Exists within a specific context

b) Has properties that characterize it

c) May participate in relationships with other information objects

d) Has provenance describing its origin and history

e) Is versioned over time

### 6.2.1 Object Identity

Each information object shall have an identity that:

- Uniquely distinguishes it within its context
- Remains stable across versions
- Is not reused for other objects
- Can be referenced by other objects

### 6.2.2 Object Type

Each information object shall have a type that:

- Classifies the object according to its nature
- Determines applicable properties and constraints
- May participate in type hierarchies

## 6.3 Property Categories

Properties of information objects fall into several categories:

### 6.3.1 Intrinsic Properties

Properties that describe essential characteristics of the information object itself:

- Creation timestamp
- Creator identification
- Current status
- Version information

### 6.3.2 Descriptive Properties

Properties that provide information about what the object represents:

- Names and labels
- Descriptions
- Classifications
- Keywords

### 6.3.3 Content Properties

Properties that carry the substantive information:

- Values and data
- Structured content
- Embedded objects
- References

### 6.3.4 Administrative Properties

Properties related to management of the information:

- Access rights
- Retention periods
- Review dates
- Disposition status

## 6.4 Value Types

Property values may be of the following types:

### 6.4.1 Atomic Types

Simple, indivisible values:

- Text values (strings, identifiers)
- Numeric values (integers, decimals)
- Boolean values
- Temporal values (dates, times)
- Binary values

### 6.4.2 Structured Types

Complex values composed of multiple parts:

- Lists (ordered collections)
- Sets (unordered collections)
- Records (named field collections)
- Trees (hierarchical structures)

### 6.4.3 Reference Types

Values that refer to other entities:

- Direct references to information objects
- Indirect references through identifiers
- External references to resources

## 6.5 Information Object Relationships

Information objects may have relationships with:

a) Other information objects

b) Agents (people, organizations, systems)

c) Activities (events, processes, actions)

d) External resources

The specification of relationships is detailed in [Clause 8](008-relationships.md).

## 6.6 Conformance

An information object conforms to UIS if it:

1. Has a unique identifier that meets the requirements of 6.2.1

2. Has a type classification as specified in 6.2.2

3. Has properties organized according to the categories in 6.3

4. Has property values that conform to the value types in 6.4

5. Participates in relationships as specified in 6.5 and Clause 8

6. Has provenance information as specified in [Clause 9](009-provenance.md)

7. Supports versioning as specified in [Clause 10](010-versioning.md)
