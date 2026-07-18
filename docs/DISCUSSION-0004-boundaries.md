# DISCUSSION-0004: Defining the Boundaries of UIS

**Discussion Number**: 0004
**Title**: What UIS Does Not Standardize
**Status**: Exploratory
**Date**: 2026-07-18
**Author**: UIS Working Group
**Related**:
- DISCUSSION-0001: What is Information?
- DISCUSSION-0002: Scope of UIS
- DISCUSSION-0003: Canonical Information Model
- ADR-0001: UIS Scope Definition

---

## 1. Introduction

### 1.1 Purpose

This document defines the conceptual boundaries of UIS by identifying what UIS does not standardize. Understanding the boundaries is essential for:

1. **Scope clarity**: Knowing what UIS does and does not address
2. **Interoperability**: Understanding where UIS fits in the broader standards landscape
3. **Extension planning**: Identifying where UIS should and should not be extended
4. **Longevity**: Ensuring UIS remains stable by excluding transient concerns

### 1.2 Relationship to Scope

UIS Scope (001-scope.md) states what UIS IS:

> "UIS establishes a universal framework for representing information in a structured, interoperable, and implementation-independent manner."

This document addresses the inverse: what UIS IS NOT. The boundaries define where UIS stops and external concerns begin.

### 1.3 The Principle of Exclusion

UIS excludes certain categories based on the principle of **implementation independence**:

> UIS shall be independent of any specific technology, language, format, or platform.

This principle implies that UIS cannot standardize categories that are inherently implementation-specific.

---

## 2. Categories Outside UIS Scope

### 2.1 Binary Encodings

**Description**: The specific binary representations used to store or transmit information.

**Examples**:
- Byte order (big-endian vs. little-endian)
- Bit encoding schemes
- Word length specifications
- Character encoding (UTF-8, UTF-16, ASCII)

**Why Outside Scope**:
1. **Technology-specific**: Binary encodings depend on hardware architecture
2. **Variable**: Different encodings suit different needs
3. **Evolutionary**: Encodings change with technology advances
4. **Domain-dependent**: Some domains require specific encodings

**Interface Point**: UIS may define constraints on what an encoding must support, but does not specify the encoding itself.

### 2.2 File Formats

**Description**: The structure and organization of files for persistence.

**Examples**:
- PDF, DOCX, HTML, Markdown
- XML schemas, JSON structure
- Image formats (PNG, JPEG, TIFF)
- Audio/video container formats

**Why Outside Scope**:
1. **Concrete implementations**: File formats are specific implementations
2. **Application-dependent**: Different formats suit different applications
3. **Standardized elsewhere**: Many file format standards already exist
4. **Technology-bound**: File formats evolve with technology

**Interface Point**: UIS information objects may be serialized in various file formats. UIS defines what information should be represented, not how it is stored.

### 2.3 Transport Protocols

**Description**: The mechanisms for moving information between systems.

**Examples**:
- HTTP, HTTPS, FTP, SMTP
- TCP/IP, UDP
- WebSocket, gRPC
- Message queues (AMQP, MQTT)

**Why Outside Scope**:
1. **Network-specific**: Protocols depend on network infrastructure
2. **Performance-focused**: Protocol choice affects performance characteristics
3. **Security-related**: Protocols include security mechanisms
4. **Operational**: Protocols are operational concerns

**Interface Point**: UIS information objects may be transmitted using various protocols. UIS defines the structure of information, not its transmission.

### 2.4 Databases

**Description**: Systems for storing and retrieving information.

**Examples**:
- Relational databases (SQL)
- Document databases (NoSQL)
- Graph databases
- Key-value stores
- Time-series databases

**Why Outside Scope**:
1. **Implementation-specific**: Database choice is an implementation decision
2. **Technology-dependent**: Database technologies evolve
3. **Query languages**: SQL, CQL, and other query languages are separate standards
4. **Schema design**: Database schema design is application-specific

**Interface Point**: UIS information objects may be stored in databases. UIS defines what information looks like, not how it is stored or queried.

### 2.5 User Interfaces

**Description**: The visual and interactive presentation of information to users.

**Examples**:
- Screen layouts
- Form designs
- Navigation structures
- Visualization components
- Accessibility features

**Why Outside Scope**:
1. **Human-specific**: User interfaces address human perception and cognition
2. **Application-specific**: UI design depends on context and audience
3. **Technology-dependent**: UIs evolve with display and interaction technologies
4. **Aesthetic**: UIs include subjective aesthetic considerations

**Interface Point**: UIS information objects may be presented via various interfaces. UIS defines information structure, not its presentation.

### 2.6 Programming Languages

**Description**: The languages used to implement systems that process information.

**Examples**:
- Python, Java, JavaScript, C#
- Type systems and type checking
- Memory management
- Language-specific libraries

**Why Outside Scope**:
1. **Language-specific**: Each language has its own paradigm
2. **Evolving**: Programming languages evolve continuously
3. **Domain-specific**: Languages suit different purposes
4. **Tooling**: Language choice affects available tooling

**Interface Point**: UIS concepts may be implemented in various languages. UIS provides abstract concepts, not language bindings.

### 2.7 Compression Algorithms

**Description**: Methods for reducing the size of information representations.

**Examples**:
- Lossless: ZIP, gzip, PNG
- Lossy: JPEG, MP3, H.264
- Dictionary-based: LZW, DEFLATE
- Specialized: genomic compression

**Why Outside Scope**:
1. **Performance-specific**: Compression affects size and speed trade-offs
2. **Content-dependent**: Different content suits different algorithms
3. **Technology-dependent**: Algorithms evolve with hardware capabilities
4. **Quality-sensitive**: Lossy compression involves quality trade-offs

**Interface Point**: UIS representations may be compressed. UIS defines information structure, not its compression.

### 2.8 Encryption Mechanisms

**Description**: Methods for securing information through cryptographic means.

**Examples**:
- Symmetric encryption (AES)
- Asymmetric encryption (RSA, ECC)
- Hashing algorithms (SHA-256)
- Key exchange protocols

**Why Outside Scope**:
1. **Security-specific**: Encryption addresses security requirements
2. **Evolving**: Cryptographic algorithms are deprecated over time
3. **Compliance-driven**: Security requirements vary by jurisdiction
4. **Separate domain**: Security is a distinct discipline

**Interface Point**: UIS representations may be encrypted. UIS defines information structure, not its security.

### 2.9 Domain-Specific Business Rules

**Description**: Rules that define how information is interpreted or processed within a specific domain.

**Examples**:
- Pricing rules in commerce
- Eligibility rules in healthcare
- Validation rules in legal documents
- Scoring rules in finance
- Classification rules in taxonomy

**Why Outside Scope**:
1. **Domain-specific**: Business rules vary by application
2. **Semantic**: Rules give meaning to information
3. **Variable**: Rules change with policy and regulation
4. **Non-universal**: What applies in one domain may not apply in another

**Interface Point**: UIS provides the structural framework for representing information subject to business rules. The rules themselves are external.

### 2.10 Additional Excluded Categories

| Category | Examples | Reason for Exclusion |
|----------|----------|---------------------|
| **Authentication** | OAuth, SAML, LDAP | Identity management is separate |
| **Authorization** | RBAC, ABAC | Access control is separate |
| **Quality of Service** | SLAs, QoS parameters | Operational concerns |
| **Physical Media** | Optical, magnetic storage | Hardware-specific |
| **Operating Systems** | Windows, Linux, macOS | Platform-specific |
| **Network Topology** | LAN, WAN, mesh | Infrastructure-specific |

---

## 3. Interface Points

### 3.1 What is an Interface Point?

An interface point is where UIS concepts meet external concerns. At interface points:

1. **UIS provides**: Abstract structure and semantics
2. **External provides**: Concrete implementation or mechanism
3. **Clear boundary**: The division of responsibility is explicit

### 3.2 UIS-Encoding Interface

```
┌─────────────────────────────────────────────────────────┐
│                    UIS Information Model                  │
│  - Entity, Property, Value                              │
│  - Relationships, Types                                 │
│  - Constraints                                          │
└─────────────────────────────────────────────────────────┘
                            │
                            │ UIS provides abstract structure
                            ▼
┌─────────────────────────────────────────────────────────┐
│                    Encoding Layer                        │
│  - Binary representation                                │
│  - Serialization format                                  │
│  - Syntax rules                                         │
└─────────────────────────────────────────────────────────┘
```

**Responsibilities**:
- UIS defines: What information must be representable
- Encoding defines: How information is physically represented

### 3.3 UIS-Transport Interface

```
┌─────────────────────────────────────────────────────────┐
│                    UIS Information Model                  │
│  - Information structure                                  │
│  - Semantic constraints                                  │
└─────────────────────────────────────────────────────────┘
                            │
                            │ UIS provides semantic content
                            ▼
┌─────────────────────────────────────────────────────────┐
│                    Transport Layer                        │
│  - Protocols                                            │
│  - Endpoints                                            │
│  - Routing                                              │
└─────────────────────────────────────────────────────────┘
```

**Responsibilities**:
- UIS defines: What information is exchanged
- Transport defines: How information is moved

### 3.4 UIS-Storage Interface

```
┌─────────────────────────────────────────────────────────┐
│                    UIS Information Model                  │
│  - Entity relationships                                  │
│  - Identity constraints                                  │
└─────────────────────────────────────────────────────────┘
                            │
                            │ UIS provides logical structure
                            ▼
┌─────────────────────────────────────────────────────────┐
│                    Storage Layer                          │
│  - Database schema                                      │
│  - Indexing strategies                                  │
│  - Query mechanisms                                     │
└─────────────────────────────────────────────────────────┘
```

**Responsibilities**:
- UIS defines: What entities and relationships exist
- Storage defines: How entities are organized for persistence

### 3.5 UIS-Presentation Interface

```
┌─────────────────────────────────────────────────────────┐
│                    UIS Information Model                  │
│  - Content and structure                                │
│  - Semantic meaning                                     │
└─────────────────────────────────────────────────────────┘
                            │
                            │ UIS provides semantic content
                            ▼
┌─────────────────────────────────────────────────────────┐
│                    Presentation Layer                     │
│  - User interface                                       │
│  - Visualization                                        │
│  - Interaction handling                                 │
└─────────────────────────────────────────────────────────┘
```

**Responsibilities**:
- UIS defines: What information means
- Presentation defines: How information is displayed

### 3.6 UIS-Security Interface

```
┌─────────────────────────────────────────────────────────┐
│                    UIS Information Model                  │
│  - Information structure                                 │
│  - Sensitivity classifications (optional)               │
└─────────────────────────────────────────────────────────┘
                            │
                            │ UIS provides sensitivity indicators
                            ▼
┌─────────────────────────────────────────────────────────┐
│                    Security Layer                         │
│  - Encryption                                           │
│  - Access control                                       │
│  - Audit logging                                        │
└─────────────────────────────────────────────────────────┘
```

**Responsibilities**:
- UIS defines: What needs protection (optionally)
- Security defines: How protection is implemented

---

## 4. Evaluation: Benefits of Exclusion

### 4.1 Interoperability Benefits

Excluding implementation-specific concerns improves interoperability:

| Exclusion | Benefit |
|-----------|---------|
| Binary encodings | Systems can exchange information regardless of internal representation |
| File formats | Information can be stored in any format while maintaining meaning |
| Transport protocols | Information can traverse any network infrastructure |
| Programming languages | Implementations can use any technology stack |

**Assessment**: Exclusion of implementation concerns ENABLES interoperability by focusing on shared semantics rather than shared implementations.

### 4.2 Longevity Benefits

Excluding transient concerns improves longevity:

| Exclusion | Benefit |
|-----------|---------|
| Specific technologies | UIS does not become obsolete when technologies change |
| Algorithm specifics | UIS does not require updates when algorithms improve |
| UI paradigms | UIS does not become dated with UI trends |
| Platform specifics | UIS works across all platforms |

**Assessment**: Exclusion of transient concerns ENHANCES longevity by ensuring UIS remains relevant as technology evolves.

### 4.3 Practical Limitations

Exclusion has practical implications:

| Concern | Implication |
|---------|-------------|
| **No wire format** | Implementations must define their own serialization |
| **No protocol** | Systems must define their own communication |
| **No storage schema** | Databases must design their own structures |
| **Integration burden** | UIS requires integration with existing standards |

**Assessment**: Exclusion shifts implementation burden to adopters but provides flexibility.

---

## 5. Comparison with Layered Standards

### 5.1 Standards Landscape

The standards landscape includes layers that interact with UIS:

```
┌─────────────────────────────────────┐
│         Presentation Standards       │  (HTML, CSS, SVG)
├─────────────────────────────────────┤
│          Document Standards          │  (PDF, Office Open XML)
├─────────────────────────────────────┤
│         Metadata Standards           │  (Dublin Core, MARC)
├─────────────────────────────────────┤
│          Domain Standards            │  (HL7, FpML, SWRL)
├─────────────────────────────────────┤
│           UIS (This Specification)   │  (Abstract Information Model)
├─────────────────────────────────────┤
│          Serialization Standards     │  (XML, JSON, RDF)
├─────────────────────────────────────┤
│          Transport Standards         │  (HTTP, MQTT, AMQP)
├─────────────────────────────────────┤
│          Network Standards           │  (TCP/IP, TLS)
└─────────────────────────────────────┘
```

### 5.2 UIS vs. Network Standards (OSI Model)

**Network Standards** (ISO/OSI model):
- Define concrete communication protocols
- Specify bit encoding, voltage levels
- Mandate specific behaviors

**UIS**:
- Defines abstract information structure
- Does not specify encoding or transmission
- Provides semantic foundation

**Relationship**: UIS operates above the network layer, providing semantic content for network transmission.

### 5.3 UIS vs. Document Standards

**Document Standards** (PDF, Office formats):
- Define specific file format structures
- Include presentation semantics
- Specify rendering behaviors

**UIS**:
- Defines domain-neutral information model
- Does not specify document structure
- Provides conceptual framework

**Relationship**: Document formats may implement UIS concepts or UIS may describe documents abstractly.

### 5.4 UIS vs. Metadata Standards

**Metadata Standards** (Dublin Core, MARC, PRISM):
- Define specific metadata vocabularies
- Target specific domains (libraries, publishing)
- Include semantic constraints

**UIS**:
- Defines structural primitives only
- Domain-neutral
- Provides modeling framework

**Relationship**: Metadata standards may be expressed using UIS primitives, or UIS may provide the underlying structure for metadata systems.

### 5.5 UIS vs. Domain Standards

**Domain Standards** (HL7 FHIR, FpML, GTIN):
- Define domain-specific information structures
- Include business semantics
- Target specific industries

**UIS**:
- Provides universal structural primitives
- Domain-neutral
- Framework for domain-specific modeling

**Relationship**: Domain standards may be defined using UIS primitives, creating alignment at the structural level while maintaining domain semantics.

### 5.6 Layered Architecture Assessment

| Layer | Relationship to UIS | Integration |
|-------|-------------------|-------------|
| Network | Independent below | UIS content over network |
| Serialization | Adjacent | UIS concepts serialized |
| UIS | This specification | Foundation |
| Metadata | Above | Metadata vocabularies |
| Domain | Above | Domain-specific extensions |
| Document | Above | Document structure |

---

## 6. Interface Design Principles

### 6.1 Principles for Clean Boundaries

UIS interface points should follow these principles:

1. **Semantic Focus**: UIS interfaces focus on semantics, not mechanisms
2. **Minimal Coupling**: UIS should not dictate external layer details
3. **Clear Responsibility**: Each layer's responsibilities should be clear
4. **Extension Points**: Interfaces should allow extension without modification
5. **Reversibility**: Changing external layers should not break UIS compliance

### 6.2 What UIS Should Specify at Interfaces

At each interface, UIS should specify:

| Interface | UIS Specifies |
|-----------|--------------|
| Encoding | What information elements must be representable |
| Transport | What information can be exchanged (semantics) |
| Storage | What entities and relationships must persist |
| Presentation | What information semantics should be conveyed |
| Security | What sensitivity levels may be indicated |

### 6.3 What UIS Should NOT Specify at Interfaces

At each interface, UIS should NOT specify:

| Interface | UIS Does NOT Specify |
|-----------|---------------------|
| Encoding | Specific formats or compression |
| Transport | Protocols or routing |
| Storage | Database schema or query language |
| Presentation | UI layouts or styles |
| Security | Specific algorithms or keys |

---

## 7. Architectural Questions for Future ADRs

### 7.1 Scope Boundary Questions

**Q1: Should UIS specify requirements at interface points?**

> Should UIS define requirements that encodings, transports, or storage must satisfy to properly support UIS information?

**Q2: Should UIS provide reference mappings?**

> Should UIS provide informative mappings to common external standards (JSON, XML, RDF)?

**Q3: Should UIS define extension points for external concerns?**

> Should UIS define where external concerns (security, quality of service) can be attached?

### 7.2 Interoperability Questions

**Q4: Does UIS interoperability require shared semantics?**

> If UIS provides only structure, is semantic interoperability achievable without additional agreements?

**Q5: Should UIS include optional semantic layers?**

> Should UIS include optional layers for common semantics (temporal, provenance)?

**Q6: How are interface conflicts resolved?**

> When external standards conflict with UIS principles, how should conflicts be resolved?

### 7.3 Integration Questions

**Q7: Should UIS reference existing standards?**

> Should UIS normative references include common external standards?

**Q8: Should UIS provide conformance testing at interfaces?**

> Should UIS conformance testing include interface compatibility?

**Q9: Should UIS profiles specify interface requirements?**

> Should domain profiles specify required interface characteristics?

### 7.4 Evolution Questions

**Q10: How does UIS handle obsolescence of external standards?**

> If a referenced external standard becomes obsolete, how should UIS respond?

---

## 8. Summary

### 8.1 Categories Outside UIS Scope

| Category | Core Reason for Exclusion |
|----------|--------------------------|
| Binary encodings | Technology-specific |
| File formats | Implementation-specific |
| Transport protocols | Network-specific |
| Databases | Persistence-specific |
| User interfaces | Human-specific |
| Programming languages | Language-specific |
| Compression | Performance-specific |
| Encryption | Security-specific |
| Business rules | Domain-specific |

### 8.2 Interface Points Identified

| Interface | UIS Role | External Role |
|-----------|----------|---------------|
| Encoding | Semantic structure | Physical representation |
| Transport | Semantic content | Movement mechanism |
| Storage | Logical structure | Physical persistence |
| Presentation | Semantic meaning | Visual display |
| Security | Sensitivity indication | Protection mechanism |

### 8.3 Benefits Assessment

| Benefit | Assessment |
|---------|-----------|
| Interoperability | **Improved** — Focus on shared semantics |
| Longevity | **Improved** — Excludes transient concerns |
| Flexibility | **Improved** — Multiple implementations possible |
| Integration burden | **Increased** — Adopters must integrate |

### 8.4 Key Insight

UIS defines the **semantic layer** of information representation, sitting between concrete implementations (encoding, storage, transport) and domain semantics (business rules, metadata vocabularies). This position provides maximum flexibility while enabling interoperability at the structural level.

---

## 9. References

1. UIS. (2026). *Scope*. Working Draft 0.3.0. `docs/001-scope.md`

2. UIS. (2026). *What is Information?* Discussion 0001. `docs/DISCUSSION-0001-information.md`

3. UIS. (2026). *Scope of UIS*. Discussion 0002. `docs/DISCUSSION-0002-scope-of-uis.md`

4. UIS. (2026). *Canonical Information Model*. Discussion 0003. `docs/DISCUSSION-0003-canonical-information-model.md`

5. UIS. (2026). *UIS Scope Definition*. ADR 0001. `docs/adr/ADR-0001-uis-scope.md`

6. UIS. (2026). *Design Principles*. Working Draft 0.3.0. `docs/004-design-principles.md`

7. UIS. (2026). *Architecture*. Working Draft 0.3.0. `docs/005-architecture.md`

---

*This is a discussion document for UIS Working Draft development. It does not constitute normative specification content.*
