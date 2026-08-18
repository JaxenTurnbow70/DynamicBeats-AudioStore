# DynamicBeats - Filesystem & Workflow

This document describes the proposed filesystem for the DynamicBeats repository and what each part is intended to do.

This is a **mock structure for discussion**, not a final implementation.

---

# Filesystem

```text
DynamicBeats/
│
├── README.md
│
├── DJs/
│   │
│   ├── DJ-Name/
│   │   ├── Music/
│   │   ├── Metadata/
│   │   └── README.md
│   │
│   └── DJ-Name/
│       ├── Music/
│       ├── Metadata/
│       └── README.md
│
├── Master-Library/
│   ├── Music/
│   ├── Metadata/
│   └── README.md
│
├── Challenges/
│   ├── Active/
│   └── Completed/
│
├── Collaborations/
│   ├── Active/
│   └── Completed/
│
├── Documentation/
│   ├── Structure.md
│   ├── Workflow.md
│   ├── Metadata.md
│   ├── Licensing.md
│   └── Telegram-Bot.md
│
└── .github/
    ├── Issues/
    └── Workflows/
```

---

# Root

## `README.md`

The front door to the repository.

It explains:

* What DynamicBeats is
* Why the repository exists
* How the system works at a high level
* Where to find things
* The current roadmap

A new DJ should be able to read this and understand the project without knowing anything about the internal structure.

---

# DJs

## `DJs/`

This is where the system starts.

Every DJ gets their own folder.

The purpose is to give each person ownership over the music they contribute while still allowing the rest of the group to access it.

```text
DJs/
└── DJ-Name/
```

A DJ can add music to their own folder.

They can also add to another DJ's folder if that DJ has given them permission.

Other DJs can take music from anyone's folder.

This creates a simple permission model without requiring complicated rules.

---

## `DJs/DJ-Name/Music/`

Contains the actual audio files that the DJ has contributed.

Initially, this is the primary location where new music enters the repository.

The organization inside `Music/` is intentionally undecided.

We should experiment before deciding whether tracks should be organized by:

* Genre
* Artist
* Album
* BPM
* Other categories

---

## `DJs/DJ-Name/Metadata/`

Contains information about the DJ's tracks.

The initial metadata should remain simple:

* Artist
* Title
* BPM
* Key
* Length
* Licensing/source
* Tags
* Notes
* Optional cue-point descriptions

Rekordbox is the reference for DJ-specific analysis.

The metadata is intended to provide a **common language between different DJ software**, rather than trying to recreate every feature of Rekordbox, Serato, or Traktor.

---
### CONSIDERATION for song file structure
Do we want to have song files and metadata structured like A
```
Artist - Track/
├── Artist - Track.mp3
└── metadata.md
```

Metadata and audio files are stored in one file named to the songs title and both follow the same naming convention. Using this format to move song information we would only need to move the folder and we would have all needed information but if you needed only the audio or only the metadata it would require individually sorting.

or like B
```
Music/
└── Artist - Track.mp3

Metadata/
└── Artist - Track.md
```
Following the same naming convention the audio and metadata are placed into separate folders. This would allow for quick movement as well but you would have to manually move the audio and the metadata of each song.

## `DJs/DJ-Name/README.md`

A small introduction to the DJ's folder.

It could eventually explain:

* Who owns the folder
* What the folder is used for
* Any special organization they're using
* Any permissions they've granted

This isn't necessary for the first version but provides a place for personal organization later and may be a great way to begin personal marketing. Think of it sort of like a linktree on instagram.

---

# Master Library

## `Master-Library/`

This is the eventual **canonical DynamicBeats library**.

It should not necessarily be populated immediately.

The long-term idea is:

> Every track that DynamicBeats actively maintains eventually has one authoritative master copy here.

The Master Library would contain the finalized audio file and its associated metadata.

---

## `Master-Library/Music/`

The master copies of approved DynamicBeats tracks.

This is what everyone should eventually pull from when building their personal working libraries.

It prevents multiple slightly different copies of the same track from becoming the group's "official" version.

---

## `Master-Library/Metadata/`

The authoritative metadata for the Master Library.

This becomes especially important if different DJs analyze the same song differently.

DynamicBeats can establish its own agreed-upon values while still using Rekordbox as the reference for DJ analysis.

---

## `Master-Library/README.md`

Explains what qualifies for the Master Library and how tracks get there.

The basic conceptual workflow is:

```text
DJ Folder
    ↓
Review
    ↓
Master Library
```

**Review** is a human decision about whether the track belongs.

**Linting** is separate and only checks that the repository's data is valid and consistent.

---

# Challenges

## `Challenges/`

Contains creative mixing challenges from telegram. This is just where it will be stored afterwards.

A challenge isn't necessarily a competition.

It is a constraint that gives us something to create.

Examples:

* Use three specified tracks.
* Mix two incompatible genres.
* Make a five-minute set.
* Create a transition using a particular technique.

The challenge should contain the prompt and whatever material is needed to participate.

---

## `Challenges/Active/`

Challenges currently available to the group.

These are things people can participate in right now.

---

## `Challenges/Completed/`

Finished challenges.

These preserve what we created and allow us to look back at previous experiments.

A completed challenge could contain:

* The original prompt
* Tracks/constraints
* Participants
* Resulting mixes
* Notes or observations

---

# Collaborations

## `Collaborations/`

Contains projects where multiple DynamicBeats members are working together.

This could eventually include:

* Collaborative DJ sets
* Shared mixes
* Track experiments
* Themed projects
* Group performances

---

## `Collaborations/Active/`

Projects currently being worked on.

---

## `Collaborations/Completed/`

Finished collaborative projects.

This gives us a record of what DynamicBeats has created together.

---

# Documentation

## `Documentation/`

Contains the rules and explanations for the repository.

These documents should answer:

> "How does DynamicBeats work?"

rather than containing music itself.

---

## `Structure.md`

Explains the reasoning behind the filesystem and how the different areas relate to one another.

This is the document to update when the architecture changes.

---

## `Workflow.md`

Explains the process a track follows through the repository.

For example:

```text
Find Music
    ↓
DJ Folder
    ↓
Metadata + Licensing
    ↓
Review
    ↓
Master Library
    ↓
Practice
    ↓
Challenges / Collaborations
    ↓
New Knowledge
```

---

## `Metadata.md`

Defines what information we track about tracks and how DJs should record it.

This should remain beginner-friendly.

For example:

> **BPM** — The tempo of the track.

> **Key** — The musical key reported by Rekordbox.

> **Notes** — Anything useful another DJ should know.

> **Cue Description** — A short explanation of what happens at a cue point.

---

## `Licensing.md`

Defines how we document where music came from and what permission DynamicBeats has to use it.

Every track should have a licensing/source designation.

It also documents the distinction between licensed music and practice-only material.

Eventually, this can describe how license documentation is associated with tracks.

---

## `Telegram-Bot.md`

Documents the eventual relationship between GitHub and the DynamicBeats Telegram group.

The intended division is:

```text
GitHub
Source of truth
      ↕
Telegram
Social / notifications
```

The bot could eventually announce repository activity, challenges, collaborations, and library proposals.

---

# `.github`

## `.github/`

Contains GitHub-specific configuration rather than DynamicBeats content.

We don't need much here initially.

---

## `.github/Issues/`

Eventually contains templates or configuration for common GitHub issues.

Potential examples:

* Add a track
* Report bad metadata
* Propose a library change
* Create a challenge
* Report a broken file

This could also provide the mechanism for group discussion and voting.

---

## `.github/Workflows/`

Eventually contains automated processes.

For example:

* Metadata checks
* File validation
* Linting
* Telegram notifications

We don't need to implement these yet.

---

# Workflow

The repository is designed around a cycle rather than a one-way upload process.

### 1. Discovery

A DJ finds music they want to practice with.

### 2. Contribution

They put it in their own `DJs/DJ-Name/Music/` folder.

### 3. Metadata

They record the basic information about the track.

Rekordbox provides the initial DJ-specific analysis.

### 4. Licensing

They identify where the track came from and tag it appropriately.

### 5. Review

When the Master Library becomes active, the group can decide whether the track belongs there.

### 6. Master Library

Approved tracks become part of the shared canonical library.

### 7. Practice

DJs use the music.

### 8. Experiment

The music becomes material for:

* Individual practice
* Mix challenges
* Collaborations
* Sets

### 9. Knowledge

DJs discover useful information about the tracks:

> "This transition works."

> "The vocal starts here."

> "This loop works over that drop."

That information can be added back to the metadata or project.

### 10. Repeat

The repository becomes a feedback loop:

```text
                 ┌───────────────┐
                 │   DISCOVERY   │
                 └───────┬───────┘
                         ↓
                 ┌───────────────┐
                 │ CONTRIBUTION  │
                 └───────┬───────┘
                         ↓
                 ┌───────────────┐
                 │   METADATA    │
                 │  + LICENSING  │
                 └───────┬───────┘
                         ↓
                 ┌───────────────┐
                 │    REVIEW     │
                 └───────┬───────┘
                         ↓
                 ┌───────────────┐
                 │     MASTER    │
                 │    LIBRARY    │
                 └───────┬───────┘
                         ↓
                 ┌───────────────┐
                 │    PRACTICE   │
                 └───────┬───────┘
                         ↓
              ┌──────────┴──────────┐
              ↓                     ↓
        MIX CHALLENGES       COLLABORATIONS
              │                     │
              └──────────┬──────────┘
                         ↓
                  NEW KNOWLEDGE
                         │
                         └──────────────→ back to library
```

The filesystem is therefore not just a way of organizing files. It is a proposed structure for how **DynamicBeats moves music, information, and creative work through the group.**

The structure should remain flexible until we've actually used it and discovered what needs to change.
