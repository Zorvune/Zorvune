# Zorvune

### Know where it is. Know who has it. Know what happened.

Zorvune is a physical asset accountability platform that helps organizations keep track of the things they own and, more importantly, keep track of what happens to them.

Computers get moved between departments. Equipment gets borrowed. Devices get assigned to different people. Tools get taken to another location and sometimes never make it back.

The problem isn't simply that organizations have a lot of assets.

The problem is that **the record and reality can slowly become different.**

Zorvune is built to keep those two connected.

---

## The Problem

Imagine an organization has this record:

```text
Laptop #1042
Department: Engineering
Location: Room 204
Assigned to: Abel
```

A few weeks later, Abel gives the laptop to another employee for a project.

Nobody updates the system.

The database still says:

```text
Engineering → Room 204 → Abel
```

But the laptop is actually:

```text
Finance → Room 112 → Someone else
```

Nothing is technically wrong with the database.

It simply no longer represents reality.

Now imagine this happening to hundreds or thousands of assets.

When something goes missing, an organization may have to ask:

* Who had it?
* Where was it last seen?
* When did it move?
* Who transferred it?
* Was the transfer recorded?
* When was the location last verified?
* Is the asset actually missing, or is the record outdated?

Zorvune exists to make those questions answerable.

---

# What Zorvune Does

Zorvune gives every physical asset a **living record**.

Instead of storing only its current information, Zorvune keeps the important events that happen throughout its life.

For example:

```text
Laptop #1042

Purchased
   ↓
Registered
   ↓
Assigned to Abel
   ↓
Moved to Room 204
   ↓
Transferred to Sara
   ↓
Moved to Finance
   ↓
Verified
```

The current location is useful.

The history explains **how it got there**.

---

# The Core Idea

Zorvune revolves around four simple questions:

### 1. What is it?

Every asset has an identity.

```text
Asset ID
Name
Serial number
Category
Condition
```

### 2. Where is it?

The system keeps track of the asset's expected location and its verification history.

```text
Expected location: Engineering / Room 204
Last verified: September 24
```

### 3. Who is responsible for it?

Instead of only storing a name in an "owner" field, Zorvune keeps track of responsibility over time.

```text
Abel
  ↓
Sara
  ↓
Engineering Department
```

### 4. What happened?

Every important change becomes part of the asset's timeline.

```text
Assigned
Transferred
Moved
Verified
Maintained
Reported missing
Recovered
Retired
```

This creates a simple but powerful idea:

> **An asset is not just a record. It has a story.**

---

# When Reality Doesn't Match the Record

This is where Zorvune becomes different from a normal inventory system.

Suppose the system expects:

```text
Laptop #1042
Expected: Room 204
```

During a verification, the laptop isn't there.

Zorvune shouldn't immediately say:

> ❌ Lost

Because nobody knows that yet.

Instead:

```text
Expected
   ↓
Not found
   ↓
Discrepancy
   ↓
Investigation
   ↓
Resolved
```

The discrepancy can then be investigated.

Maybe:

```text
→ The laptop was transferred
→ Someone borrowed it
→ It was moved to another room
→ The location record was never updated
→ The asset is actually missing
```

Once the situation is understood, the record can be updated while preserving what happened.

---

# The Asset Timeline

Every asset has a timeline that tells its story.

Example:

```text
September 02
Asset registered
        ↓
September 05
Assigned to Abel
        ↓
September 12
Moved to Room 204
        ↓
September 18
Transferred to Sara
        ↓
September 24
Expected in Room 204
        ↓
September 24
Not found
        ↓
September 25
Discrepancy investigated
        ↓
September 25
Found in Finance
```

Instead of looking at a database row and trying to figure out what happened, the organization can follow the timeline.

---

# Why This Matters

Without a clear history, an organization might know:

> "This laptop is missing."

With a clear history, it can know:

> "This laptop was last verified in Engineering, was transferred to Sara three days later, and was expected in Room 204 when it wasn't found."

That difference matters when dealing with expensive equipment, shared resources, accountability, and large organizations.

---

# Zorvune's Main Building Blocks

## Assets

A central place for all physical assets.

Examples:

* Laptops
* Phones
* Projectors
* Cameras
* Tools
* Printers
* Laboratory equipment
* Office equipment
* Vehicles
* Other organizational property

---

## People & Departments

Connect assets to the people and departments responsible for them.

```text
Person
Department
Role
Assigned assets
```

---

## Locations

Organize physical locations inside an organization.

```text
Organization
 ├── Building A
 │    ├── Floor 1
 │    └── Floor 2
 │
 └── Building B
      ├── Office 101
      └── Office 102
```

---

## Transfers

Record when an asset moves from one person, department, project, or location to another.

```text
FROM
Engineering / Abel

        ↓

TO
Finance / Sara
```

The transfer becomes part of the asset's permanent timeline.

---

## Verification

Allow an organization to check whether its physical assets match its records.

For example:

```text
Expected: 25 assets
Verified: 23 assets

2 discrepancies found
```

The important part is that the organization can then investigate those discrepancies instead of simply changing numbers.

---

## Discrepancies

When something doesn't match, Zorvune records it.

A discrepancy can have:

```text
Asset
Expected state
Observed state
Date
Reported by
Status
Investigation notes
Resolution
```

This turns:

> "Something is wrong."

into:

> "Something is wrong, here's what was expected, what was observed, who reported it, and what happened afterward."

---

# A Simple Example

A school owns 100 laptops.

The system knows:

```text
100 registered
96 currently assigned
4 in storage
```

During a verification, one laptop expected in the computer lab isn't found.

Instead of deleting it or changing its location manually:

```text
Laptop #037
Status: Discrepancy
Expected: Computer Lab
Last verified: Computer Lab
```

The administrator investigates.

They discover that a teacher took it to another classroom.

The record is updated:

```text
Laptop #037
New location: Classroom 12
Custodian: Teacher X
```

But the original discrepancy remains in the history.

Now the organization knows both:

**where the laptop is now**

and

**why the previous record was wrong.**

---

# Designed Around Accountability

Zorvune is not trying to make organizations manually enter more information just for the sake of having more data.

The goal is to make important changes understandable.

When something moves, there should be a reason.

When responsibility changes, there should be a record.

When an asset cannot be found, there should be an investigation.

When a discrepancy is resolved, the organization should still be able to see what happened.

---

# From Inventory to Accountability

Traditional inventory thinking:

```text
What do we have?
```

Zorvune:

```text
What do we have?
        +
Where is it?
        +
Who is responsible?
        +
When was it last verified?
        +
What changed?
        +
What happened when reality didn't match the record?
```

That is the core of Zorvune.

---

# Project Structure

Zorvune is designed around a simple workflow:

```text
REGISTER
   ↓
ASSIGN
   ↓
MOVE
   ↓
VERIFY
   ↓
MATCH ────────────────┐
   │                  │
   │                  │
   └── MISMATCH       │
          ↓           │
     INVESTIGATE      │
          ↓           │
       RESOLVE ───────┘
```

The result is a continuous asset history rather than a collection of disconnected records.

---

# Who Is Zorvune For?

Zorvune can be used by organizations that manage physical property across multiple people or locations, including:

* Schools and universities
* Companies
* NGOs
* Hospitals
* Laboratories
* Government organizations
* Workshops
* Offices
* Warehouses

Anywhere physical assets move, accountability can become difficult.

---

# Vision

Zorvune's goal is simple:

**Make physical assets accountable.**

Not just by telling an organization what it owns, but by keeping track of the relationship between the asset, its location, its custodian, and the events that happen throughout its life.

Because when an organization asks:

> **"What happened to this asset?"**

the answer shouldn't require searching through spreadsheets, messages, paper forms, and people's memories.

It should be in the asset's story.

---

## Zorvune

**Know where it is.
Know who has it.
Know what happened.**
