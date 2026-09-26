# Zorvune

### The accountability layer between physical assets and digital records.

**Zorvune** is a physical asset accountability platform designed to solve a simple but overlooked problem:

> **A database can say where an asset is. That doesn't mean the asset is actually there.**

Organizations manage computers, equipment, tools, devices, furniture, laboratory assets, and other physical property through digital records. But physical assets constantly move through offices, departments, employees, projects, and locations.

Records don't always move with them.

An asset can be transferred without being recorded, borrowed by another department, misplaced, damaged, or left at a different location while the system continues showing its previous state.

Zorvune focuses on closing that gap.

---

## The Problem

Traditional asset management systems are built around records:

```text
Asset → Location
Asset → Owner
Asset → Status
```

But physical reality is not static.

```text
Digital record:
Laptop-042 → IT → Room 204 → Employee A

Physical reality:
Laptop-042 → Finance → Room 118
                 ↑
            never recorded
```

The result is an organization that may have a complete-looking inventory while lacking a reliable understanding of what is actually happening to its assets.

This creates questions that ordinary inventory systems struggle to answer:

* Where was the asset actually verified?
* When was it last physically confirmed?
* Who was responsible for it at the time?
* Has it changed location since the last verification?
* What happened between two recorded events?
* Is the record wrong, or did reality change?
* Can the asset's history be trusted?

**Zorvune is built around these questions.**

---

# Why Zorvune?

Research reviewed during the development of Zorvune identified several weaknesses in current approaches to physical asset management.

Research on RFID verification demonstrates that systems can efficiently identify missing or unreadable tags, but detecting a discrepancy does not necessarily explain why it occurred.

Research on enterprise asset ownership has shown that ownership information can be incomplete enough that machine-learning methods are used to reconstruct which team owns an asset.

Research on physical tracking also demonstrates that location measurements have different levels of accuracy depending on the technology and environment.

Meanwhile, asset maintenance and replacement research relies on historical per-asset information to make lifecycle decisions.

Together, these findings point to a larger problem:

> **Organizations can maintain digital records of their physical assets without maintaining a reliable connection between those records and physical reality.**

Zorvune is designed around that connection.

---

# Core Idea

Zorvune treats an asset as more than a row in a database.

Each asset has a history.

```text
                    ┌── Location
                    │
                    ├── Custodian
                    │
Asset ──────────────┼── Verification
                    │
                    ├── Maintenance
                    │
                    ├── Transfers
                    │
                    └── Discrepancies
```

Instead of only asking:

> "Where does the database say this asset is?"

Zorvune is built to ask:

> **"What evidence do we have about this asset's current state?"**

---

# The Zorvune Model

## 1. Asset Identity

Every physical asset has a persistent digital identity connecting the real-world object to its record.

The identity becomes the anchor for everything that happens to the asset throughout its lifecycle.

---

## 2. Custody

An asset's current custodian is only part of the story.

Zorvune treats responsibility as a history:

```text
Employee A
    ↓
IT Department
    ↓
Employee B
    ↓
Engineering
```

This makes it possible to understand how responsibility changed instead of relying on a single current-owner field.

---

## 3. Location

A location should not be treated as an eternal fact.

A useful location record has context:

```text
Location
Timestamp
Verification source
Verification status
Confidence / uncertainty
```

This creates an important distinction between:

**"The system says it is here."**

and

**"It was physically verified here recently."**

---

## 4. Verification

Physical verification is where the digital record meets reality.

A verification event can establish whether an expected asset was physically observed.

But a failed verification does not automatically mean:

```text
ASSET = LOST
```

It means:

```text
EXPECTED
   ↓
NOT VERIFIED
   ↓
DISCREPANCY
   ↓
INVESTIGATION
```

The distinction matters.

A missing asset, an outdated record, a damaged identifier, and an asset temporarily moved elsewhere are different situations.

---

## 5. Discrepancies

Zorvune treats discrepancies as first-class events rather than simply changing a database field.

An asset can move through states such as:

```text
Verified
   ↓
Expected
   ↓
Not Found
   ↓
Under Investigation
   ↓
Resolved
```

The important part is preserving **what happened**, rather than silently overwriting the previous state.

---

## 6. Asset History

A physical asset accumulates a history throughout its lifecycle.

```text
Procured
   ↓
Registered
   ↓
Assigned
   ↓
Transferred
   ↓
Verified
   ↓
Maintained
   ↓
Transferred
   ↓
Verified
   ↓
Retired
```

This history provides the context needed to understand the asset's current state.

---

# Example

Consider an organization with 500 computers.

The system contains:

```text
Laptop #237
Department: Engineering
Room: 204
Custodian: Employee A
```

During the next physical verification, Laptop #237 cannot be found.

A conventional inventory system may simply produce:

```text
❌ Missing
```

But that creates more questions than answers.

Zorvune treats the situation as a discrepancy:

```text
Laptop #237
       │
       ├── Last verified: Room 204
       ├── Last custodian: Employee A
       ├── Expected location: Engineering
       │
       ↓
Physical verification
       │
       ↓
Not observed
       │
       ↓
Discrepancy created
       │
       ↓
Investigation
       │
       ├── Transferred?
       ├── Borrowed?
       ├── Relocated?
       ├── Identifier damaged?
       └── Actually missing?
```

The objective is not simply to count missing assets.

It is to preserve the chain of evidence needed to understand **what happened**.

---

# What Makes the Problem Interesting?

The difficult part of physical asset management is not storing:

```text
name
serial number
location
owner
```

Those are easy.

The difficult part is maintaining the connection between:

```text
DIGITAL RECORD
      ↕
PHYSICAL REALITY
```

over time.

Physical reality changes continuously.

Digital records change when someone records those changes.

That difference creates the **Zorvune Problem**.

---

# Research Foundation

Zorvune's problem definition is grounded in research covering:

* Physical asset verification
* RFID missing-tag identification
* Barcode and QR recognition
* Enterprise asset ownership
* Asset location tracking
* Maintenance optimization
* Asset lifecycle management
* Supply-chain traceability
* Tamper-evident provenance
* Traceability adoption

Selected research:

### Asset verification

Liu et al., *Revisiting RFID Missing Tag Identification*

https://arxiv.org/abs/2510.18285

Research on missing-tag identification demonstrates that the problem of identifying expected-but-unreadable physical tags can be formally modeled and efficiently solved.

### Enterprise ownership

Jacobik, *Asset Ownership Identification: Using Machine Learning to Predict Enterprise Asset Ownership*

https://arxiv.org/abs/2312.10266

The study demonstrates that enterprise asset ownership can be sufficiently incomplete that ownership has to be inferred from other organizational and network attributes.

### Physical tracking

Hateley et al., *Camera-RFID Fusion for Robust Asset Tracking in Forested Environments*

https://arxiv.org/abs/2604.26241

The research demonstrates that different tracking technologies have different accuracy and failure characteristics, highlighting the importance of understanding the uncertainty behind a location observation.

### Asset lifecycle

Cesca & Novaes, *Physical Assets Replacement: An Analytical Approach*

https://arxiv.org/abs/1210.3678

The work models replacement decisions using accumulated capital and maintenance costs over an asset's lifecycle.

### Maintenance optimization

Verleijsdonk et al., *Maintenance Optimization for Asset Networks with Unknown Degradation Parameters*

https://arxiv.org/abs/2410.18246

The research demonstrates the importance of historical per-asset information for data-driven maintenance decisions.

### Traceability

Blaettchen et al., *Traceability Technology Adoption in Supply Chain Networks*

https://arxiv.org/abs/2104.14818

The study examines how traceability benefits depend on adoption across interconnected participants.

---

# Project Direction

Zorvune is being developed as a platform for organizations that need stronger accountability over physical assets.

The project is focused on one principle:

> **Don't just store what the organization believes about an asset. Preserve the evidence of what actually happened to it.**

The goal is to make asset records more understandable, traceable, and connected to physical verification.

---

# Project Status

🚧 **Active development**

Zorvune is currently being developed as part of the **STARK Official Hackathon**.

The project is evolving through research, prototyping, and validation of the core physical-asset accountability problem.

---

# Vision

Organizations should not need to wait for an annual inventory count to discover that their digital asset records stopped matching reality months ago.

Zorvune aims to make the relationship between an organization's **assets, people, locations, events, and evidence** visible throughout the asset lifecycle.

### Zorvune

**Know what you own.
Know where it is.
Know who was responsible.
Know what happened.**
