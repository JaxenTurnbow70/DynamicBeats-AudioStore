## Permissions & Ownership

Initially, each DJ has their own folder.

A DJ can:

* Add music to their own folder
* Take music from another DJ’s folder
* Add to another DJ’s folder only when they have permission

This keeps responsibility for contributed music clear while still allowing the group to share freely.

---

## Future Master Library

As the system matures, we can introduce a Master Library.

The Master Library would contain the approved master copy and metadata for every track that DynamicBeats accepts into its active collection.

The intended relationship would be:

**DJ folders → Review → Master Library → Shared access**

This gives us a gradual path from individual contributions toward a properly curated collective library without requiring that system on day one.

> **Note:** “Review” is a human or automated validation step. It is not linting.

---

## Linting

Linting is a **validation and cleanup process**, not a curation process.

Its purpose is to ensure the repository stays consistent and free of outdated or invalid data.

Linting should:

* Remove or flag **broken references** (missing files, invalid paths)
* Detect **outdated metadata formats**
* Enforce **required fields** (e.g. BPM, Key, Title if mandated)
* Normalize formatting (consistent tags, naming conventions)
* Identify **stale entries** that no longer match the actual audio file

Linting should NOT:

* Decide whether a track is “good”
* Approve or reject music for the library
* Move tracks into the Master Library
* Perform editorial judgment

In short:

> **Linting keeps the data clean. Review decides what belongs.**

---

## Metadata

For now, metadata should stay simple and portable between DJ software.

Our initial standard can include:

* Artist
* Title
* BPM
* Key
* Length
* Notes
* Tags
* Licensing/source
* Optional cue-point descriptions

**I assume Rekordbox will be our reference for DJ-specific analysis when it comes to apps giving contradictory data.**

The goal is not to copy every piece of information from the software. We simply want a common set of information that DynamicBeats agrees is useful.

If someone adds a cue point, they can describe what it represents:

> `01:32 — Vocal entrance`

rather than trying to recreate the entire DJ software database.

This keeps the information understandable even when DJs use different software.
