# DISCUSSION-0001: What is Information?

**Discussion Number**: 0001
**Title**: Fundamental Concepts of Information
**Status**: Exploratory
**Date**: 2026-07-18
**Author**: UIS Working Group
**Purpose**: Investigate the nature of information to inform UIS terminology decisions

---

## 1. Introduction

This document explores the fundamental question of what constitutes "information." The purpose is not to adopt a definition, but to understand the landscape of perspectives, identify commonalities, and surface conflicts that require architectural decisions.

UIS must take a position on information, but that position should be informed by established thinking across multiple disciplines.

---

## 2. Survey of Perspectives

### 2.1 Information Theory (Shannon)

**Origin**: Claude Shannon's 1948 paper "A Mathematical Theory of Communication"

**Definition**: Information is a measure of uncertainty reduction. Specifically, information is the decrease in uncertainty about the state of a system upon receiving a message.

**Key Concepts**:
- **Entropy**: The measure of uncertainty or randomness in a system
- **Bit**: The fundamental unit of information (binary choice)
- **Signal vs. Noise**: Information is distinguished from random noise
- **Channel Capacity**: Maximum rate of information transfer

**Core Thesis**: Information is independent of meaning. A random string of bits contains as much information as meaningful text of the same length, according to Shannon.

**Implications**:
- Information is quantitative, not qualitative
- Meaning is irrelevant to information content
- Information can be measured without understanding

**Questions Raised**:
- Is Shannon information sufficient for UIS purposes?
- Does UIS require meaning-bearing information?

### 2.2 Semantic Information Theory

**Origin**: Responses to Shannon, including works by Yehoshua Bar-Hillel, Rudolf Carnap, Luciano Floridi

**Definition**: Semantic information is information that is "well-formed" and "meaningful."

**Key Concepts**:
- **Data**: Raw symbols without interpretation
- **Meaning**: Relationship between data and what it represents
- **Truth**: Semantic information must be true to be information
- **Relevance**: Information must be relevant to the receiver

**Core Thesis**: Shannon information is necessary but not sufficient. Information that is syntactically correct but semantically meaningless or false does not constitute information in the full sense.

**Implications**:
- Information requires context and interpretation
- False information is not information (per some theories)
- The receiver's knowledge state matters

**Questions Raised**:
- Can UIS address semantic information?
- Is UIS scope syntactic, semantic, or both?

### 2.3 Philosophy (Epistemology)

**Origin**: Classical epistemology; Plato, Aristotle; modern thinkers including Gettier, Goldman

**Definition**: Information is a type of "justified true belief" or the evidence that supports belief.

**Key Concepts**:
- **Belief**: A mental state of acceptance that something is true
- **Justification**: The grounds for holding a belief
- **Truth**: Correspondence to reality or coherence with other beliefs
- **Knowledge**: Justified true belief (classical definition)

**Classical Definition**: S knows that P if and only if:
1. P is true
2. S believes that P
3. S is justified in believing that P

**Gettier Problems**: Edmund Gettier showed in 1963 that the classical definition fails in certain cases where someone has a justified true belief that doesn't constitute knowledge.

**Implications**:
- Information is tied to truth and belief
- Information has epistemic value
- The relationship between information and knowledge is complex

**Questions Raised**:
- Does UIS information require truth?
- Can UIS address beliefs and justification?

### 2.4 Knowledge Representation (Artificial Intelligence)

**Origin**: AI research; McCarthy, Hayes, Davis, Shrobe

**Definition**: Information is structured data that can be processed by automated reasoning systems.

**Key Concepts**:
- **Ontology**: A formal specification of a conceptualization
- **Knowledge Base**: A collection of assertions about the world
- **Inference**: Deriving new information from existing information
- **Semantic Network**: Graph structure representing concepts and relationships

**Frame Problem**: The difficulty of specifying which consequences of actions should be represented.

**Implications**:
- Information must be machine-processable
- Information structure enables reasoning
- Representations must be complete enough for intended purposes

**Questions Raised**:
- Does UIS require machine-processable information?
- What is the role of inference in UIS?

### 2.5 Systems Engineering

**Origin**: Systems theory; Bertalanffy, Wiener, Checkland

**Definition**: Information is data that has been processed and presented in a form suitable for decision-making.

**Key Concepts**:
- **Data**: Raw observations or measurements
- **Information**: Processed data with context and meaning
- **Wisdom/Knowledge**: Understanding of information in context
- **Feedback**: Information about system state used for control

**DIKW Hierarchy** (Data, Information, Knowledge, Wisdom):
```
Data → Information → Knowledge → Wisdom
```

**Implications**:
- Information is value-added data
- Information serves decision-making
- Information is relative to context and purpose

**Questions Raised**:
- Does UIS adopt the DIKW hierarchy?
- What is the relationship between data and information in UIS?

### 2.6 Library and Information Science

**Origin**: Documentation science; Otlet, Shera; modern LIS theory

**Definition**: Information is recorded knowledge communicated through media.

**Key Concepts**:
- **Document**: Any recorded information artifact
- **Retrieval**: Finding information relevant to a need
- **Relevance**: The usefulness of information for a specific purpose
- **Bibliographic Record**: Structured description of documents

**Implications**:
- Information is persistent and communicable
- Information exists independently of receivers
- Information can be stored and retrieved

**Questions Raised**:
- Does UIS address physical or digital documents?
- Is information dependent on human interpretation?

---

## 3. Comparison of Definitions

| Perspective | Information Requires | Information Does NOT Require |
|-------------|---------------------|----------------------------|
| Shannon | Uncertainty reduction | Meaning, truth, usefulness |
| Semantic | Well-formedness, meaning | Quantification |
| Epistemology | Truth, justification | Objective measurement |
| Knowledge Rep. | Machine-processability | Human interpretation |
| Systems Eng. | Decision utility | Independence from context |
| LIS | Persistence, communicability | Current relevance |

### 3.1 Points of Agreement

Across all perspectives, information appears to share certain characteristics:

1. **Structured**: Information is not random; it has organization
2. **Relational**: Information exists in relation to something else (truth, receiver, system)
3. **Processable**: Information can be acted upon (transmitted, stored, reasoned about)
4. **Communicable**: Information can be conveyed from one entity to another
5. **Contextual**: Information meaning depends on context of interpretation

### 3.2 Points of Disagreement

1. **Truth Requirement**: Some definitions require truth; others do not
2. **Meaning Requirement**: Some definitions require semantic content; others do not
3. **Subjectivity**: Some definitions are receiver-dependent; others are objective
4. **Quantifiability**: Some definitions allow measurement; others resist quantification
5. **Purpose**: Some definitions are purpose-neutral; others require usefulness

---

## 4. Distinguishing Data, Information, Knowledge, Evidence

### 4.1 The DIKW Model

The most common framework distinguishes:

```
Data → Information → Knowledge → Wisdom
```

### 4.2 Data

**Definition**: Raw, unprocessed facts without context or interpretation.

**Characteristics**:
- Objective observations
- No inherent meaning
- Format-independent
- Examples: sensor readings, transaction logs, survey responses

**Debate**: Some argue data is meaningless symbols; others argue data always carries implicit interpretation.

### 4.3 Information

**Definition**: Data that has been processed, organized, or structured to provide meaning.

**Characteristics**:
- Data + Context = Information
- Purposeful organization
- Interpretable without additional transformation
- Examples: sorted lists, formatted reports, indexed records

**Debate**: The threshold between data and information is disputed. Is one data point information?

### 4.4 Knowledge

**Definition**: Information that has been internalized, understood, and integrated with existing understanding.

**Characteristics**:
- Personal or organizational
- Actionable
- Includes tacit understanding
- Examples: expertise, institutional memory, learned skills

**Debate**: Can knowledge exist without a knower? Is knowledge a state or a process?

### 4.5 Evidence

**Definition**: Information that supports or substantiates a claim or assertion.

**Characteristics**:
- Supports reasoning about other information
- Tied to assertions or propositions
- May be stronger or weaker depending on type and source
- Examples: citations, measurements, testimonies, records

**Debate**: Is evidence a type of information, or a relationship between information and claims?

### 4.6 Proposed Distinctions for UIS Consideration

| Concept | UIS Characteristic (Under Investigation) |
|---------|----------------------------------------|
| Data | Raw, uninterpreted; format-dependent |
| Information | Structured, contextualized; meaning-bearing |
| Knowledge | Internalized, actionable; agent-dependent |
| Evidence | Supportive, evidential; assertion-related |

**Open Question**: Should UIS distinguish these concepts, and if so, how?

---

## 5. Universal Concepts Identified

The following concepts appear across multiple perspectives and may be candidates for inclusion in UIS:

### 5.1 Entity

Something that can be identified and distinguished from other things. Appears in:
- Knowledge representation (objects, concepts)
- Systems engineering (system components)
- Philosophy (particulars, substances)
- Library science (documents, subjects)

### 5.2 Property

A characteristic or attribute of an entity. Appears in:
- Knowledge representation (attributes, slots)
- Philosophy (properties, qualities)
- Systems engineering (parameters, states)

### 5.3 Relationship

A connection between entities. Appears in:
- Knowledge representation (relations, links)
- Semantic networks (edges, associations)
- Systems engineering (flows, dependencies)

### 5.4 Value

A specific instance of a property. Appears in:
- Knowledge representation (values, fillers)
- Database theory (cell values, field contents)
- Systems engineering (measurements, readings)

### 5.5 Type/Category

A classification of entities or properties with common characteristics. Appears in:
- Knowledge representation (classes, types)
- Philosophy (universals, categories)
- Library science (subject headings, classification)

### 5.6 Identifier

A means of distinguishing one entity from another. Appears in:
- Database theory (primary keys)
- Library science (identifiers, accession numbers)
- Semantic web (URIs, IRIs)

### 5.7 Representation

A concrete form or encoding of information. Appears in:
- Knowledge representation (encoding, formalism)
- Shannon theory (message, signal)
- Systems engineering (display, interface)

---

## 6. Conflicts Requiring Resolution

### 6.1 Syntactic vs. Semantic Information

**Conflict**: Shannon information excludes meaning; semantic information requires it.

**Implications for UIS**:
- If UIS adopts Shannon-like information: broad applicability, no semantic claims
- If UIS adopts semantic information: richer model, domain dependencies
- Hybrid approach possible: syntactic foundation, semantic extension

**Architectural Decision Required**: Does UIS address meaning, or only structure?

### 6.2 Objective vs. Subjective Information

**Conflict**: Some theories treat information as objective (independent of receiver); others treat it as subjective (dependent on receiver's knowledge).

**Implications for UIS**:
- Objective: Universal representations possible, receiver-independent
- Subjective: Context-dependent, may vary across receivers
- Relational: Information is about the relationship between representation and reality

**Architectural Decision Required**: Is UIS information objective, subjective, or relational?

### 6.3 Truth Requirement

**Conflict**: Some definitions require truth; others do not. Shannon explicitly excludes truth; epistemology requires it.

**Implications for UIS**:
- If truth required: UIS can support knowledge claims, but cannot handle false information
- If truth excluded: UIS can handle any representation, but cannot support truth claims
- Evidential approach: UIS tracks evidence without claiming truth

**Architectural Decision Required**: Does UIS information require truth?

### 6.4 Agent-Dependence

**Conflict**: Some definitions treat information as existing independently of agents; others treat it as inherently related to knowers or systems.

**Implications for UIS**:
- Agent-independent: Pure representation model
- Agent-dependent: Information tied to receivers or systems
- Hybrid: Information can exist, but its significance depends on agents

**Architectural Decision Required**: Is UIS information agent-independent or agent-relative?

### 6.5 Data-Information Distinction

**Conflict**: The boundary between data and information is disputed.

**Implications for UIS**:
- If distinction recognized: UIS applies to information only
- If distinction rejected: UIS applies to data and information equally
- If hierarchical: UIS may define levels (data, information, knowledge)

**Architectural Decision Required**: Should UIS distinguish data from information?

---

## 7. Open Questions for Architectural Decisions

The following questions require architectural decisions before UIS terminology can be finalized:

### 7.1 Scope Decision: What is UIS Information?

> Does UIS information refer to:
> - Any structured data (broad interpretation)
> - Meaning-bearing information (semantic interpretation)
> - Evidence-bearing information (evidential interpretation)

### 7.2 Objectivity Decision: Information Nature

> Is UIS information:
> - Objective and receiver-independent
> - Subjective and receiver-dependent
> - Relational, about representation-reality correspondence

### 7.3 Truth Decision: Truth Requirement

> Does UIS information:
> - Require truth for validity
> - Exclude truth claims entirely
> - Track truth-related evidence without claiming truth

### 7.4 Agent Decision: Role of Agents

> Does UIS information:
> - Exist independently of agents
> - Require agents for interpretation
> - Include agent perspectives as part of the model

### 7.5 Hierarchy Decision: DIKW Model

> Should UIS:
> - Adopt the DIKW hierarchy (data, information, knowledge, wisdom)
> - Treat data and information uniformly
> - Define a different conceptual structure

### 7.6 Entity Decision: Primitives

> Should UIS define as primitives:
> - Entity, property, value, relationship
> - Information object, assertion, evidence
> - Something else entirely

### 7.7 Encoding Decision: Representation Scope

> Should UIS address:
> - Only abstract structure (no encoding concerns)
> - Encoding requirements for interoperability
> - Specific encodings for particular domains

---

## 8. Summary

This discussion document has surveyed multiple perspectives on information, compared definitions, identified commonalities and conflicts, and proposed distinctions between data, information, knowledge, and evidence.

**Common Characteristics of Information**:
- Structured and organized
- Relational (tied to truth, receivers, or systems)
- Processable and communicable
- Contextual in meaning

**Major Conflicts**:
- Syntactic vs. semantic information
- Objective vs. subjective information
- Truth requirement vs. truth-independence
- Agent-dependence vs. agent-independence
- Data-information distinction

**Candidates for UIS Primitives**:
- Entity, property, value, relationship
- Type/category, identifier, representation

The open questions in Section 7 must be resolved through Architectural Decision before UIS terminology can be finalized.

---

## 9. References

1. Shannon, C. E. (1948). A Mathematical Theory of Communication. *Bell System Technical Journal*, 27(3), 379–423.

2. Bar-Hillel, Y., & Carnap, R. (1953). Semantic Information. *British Journal for the Philosophy of Science*, 4(14), 147–157.

3. Floridi, L. (2004). Semantic Conceptions of Information. *Stanford Encyclopedia of Philosophy*.

4. Gettier, E. (1963). Is Justified True Belief Knowledge? *Analysis*, 23(6), 121–123.

5. Davis, R., Shrobe, H., & Szolovits, P. (1993). What Is a Knowledge Representation? *AI Magazine*, 14(1), 17–33.

6. Ackoff, R. L. (1989). From Data to Wisdom. *Journal of Applied Systems Analysis*, 16, 3–9.

7. Otlet, P. (1935). *Traité de Documentation*. Brussels: Mundaneum.

8. Checkland, P., & Scholes, J. (1990). *Soft Systems Methodology in Action*. Chichester: Wiley.

---

*This is a discussion document for UIS Working Draft development. It does not constitute normative specification content.*
