# DynamicBeats - Telegram Bot

The DynamicBeats Telegram bot will connect our GitHub repository with the Telegram group we already use.

The goal is not to move the library into Telegram.

**GitHub remains the source of truth. Telegram becomes the social and notification layer.**

## What It Could Do

### Repository Updates

Notify the Telegram group when something important happens:

* New music is added
* A mix challenge is created
* A collaboration is started
* A useful contribution is made
* A library proposal is opened or resolved

Example:

> 🎵 **New Track Added**
> Jaxen added *Artist — Track*
> 174 BPM · F♯ minor
> [View in GitHub]

### Mix Challenges

When a new challenge is created in GitHub, the bot can announce it in Telegram.

The challenge could be something like:

> **Challenge #04**
> Given these three tracks, create a 5-minute mix.
> Any technique allowed.

Telegram becomes the place where people discuss and share their attempts.

### Library Proposals

If we use GitHub Issues or Discussions to propose changes to the library, Telegram can notify everyone.

Example:

> 📊 **Library Proposal**
> Should this track move to the DnB collection?
> 👍 6 · 👎 1
> [Discuss / Vote]

### Collaborations

The bot could announce new collaborative projects and link directly to them.

This keeps the social conversation in Telegram while keeping the actual project files and history in GitHub.

## Future Possibilities

Eventually the bot could allow limited interaction with GitHub from Telegram.

For example:

* Submit a practice note
* Start a challenge
* Report a useful transition
* Submit a track for review
* View the current challenge
* View recent contributions

These should be considered **future features**, not requirements for the initial repository.

## Design Principle

We should avoid duplicating information between Telegram and GitHub.

```text
GitHub
  ↓
Source of truth

Telegram
  ↓
Discussion
Notifications
Social interaction
```

If something needs to be permanently recorded, it should ultimately live in GitHub.

## Roadmap

### Phase 1

* [ ] GitHub → Telegram notifications
* [ ] New track notifications
* [ ] Challenge notifications
* [ ] Collaboration notifications

### Phase 2

* [ ] Library proposal notifications
* [ ] Links back to relevant GitHub discussions
* [ ] Recognition/contribution announcements

### Phase 3

* [ ] Telegram → GitHub submissions
* [ ] Challenge interaction
* [ ] Practice notes
* [ ] Track submissions
