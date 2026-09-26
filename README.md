# Zorvune

**Making physical assets accountable to reality.**

Zorvune is a research-driven project focused on a problem that organizations face when managing physical assets: the gap between what their digital records say and what is actually happening to the physical assets.

An asset can have a recorded owner, location, status, and history, while the physical reality may have already changed. An asset may move, be handed over, become damaged, go missing, or simply stop matching what the system says — without that change being captured at the moment it happens.

## The Problem

Existing research shows several weaknesses in organizational physical asset management:

* Physical verification can identify missing or unreadable asset tags, but detecting a discrepancy does not explain what actually happened.
* Enterprise ownership records can be incomplete enough that ownership has to be inferred from other information.
* Asset location is not absolute; different identification technologies have different accuracy and limitations.
* Maintenance and replacement decisions depend on historical asset data, yet the reliability and completeness of that history are often assumed rather than established.
* Tamper-resistant records can protect information after it is recorded, but they cannot guarantee that the original observation was correct.

This creates a fundamental gap:

> **The digital record represents what was recorded. The physical asset represents what is actually happening. These two can diverge without the organization knowing exactly when, why, or how.**

## Research

Zorvune is being developed from existing research rather than starting with a technology-first solution.

Our current research focuses on:

* physical asset verification
* asset ownership and custody
* asset location uncertainty
* lifecycle history
* discrepancy detection
* traceability
* record integrity
* the gap between digital records and physical reality

The current research and problem definition are being documented in this organization.

## Current Research Direction

We are currently investigating three connected formulations of the problem:

1. **The Observability Gap**
   Physical assets can change between recorded events, leaving digital records out of sync with reality.

2. **The Accountability-Reconstruction Problem**
   Asset responsibility may need to be reconstructed from incomplete records instead of being reliably recorded when custody changes.

3. **The Trust-in-History Problem**
   Decisions about maintenance and replacement depend on historical asset data, while the fidelity of that history is not always known.

These are currently research hypotheses and problem formulations, not final product features.

## Project Status

**Stage: Problem Definition & Research**

We are currently validating the problem, reviewing existing research, identifying gaps, and defining the exact problem Zorvune should address.

No final solution architecture has been locked in yet.

## Repository Structure

```text
Zorvune/
├── research/
│   ├── papers/
│   ├── findings/
│   └── problem-definition/
├── docs/
├── prototypes/
└── README.md
```

## Research Principle

Zorvune is being built around a simple principle:

**Don't start with the technology. Start with the problem.**

The goal is to understand where existing asset-management systems lose connection with physical reality, determine what remains poorly addressed by existing research, and only then design the appropriate system.

---

**Zorvune — Researching the gap between what organizations record and what physically exists.**
