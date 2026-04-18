---
date: YYYY-MM-DD
type: daily-log
tags: [session-log]
session-count: 0
---

# YYYY-MM-DD Session Log

A daily log is append-only. Every atomic unit of work lands here as a timestamped entry. The file opens at session start via a hook; the session-end ritual commits it and writes a handoff note to the next session.

## Active Context
- Project:
- Goal:
- Handoff from previous session: [[previous-daily-log]]

## Timeline

<!-- Append-only entries. One entry per completed unit of work. Format:

## HH:MM - [category] Title
Short description. [[referenced-note]] updated.

Categories: infrastructure, decision, bug-fix, discovery, code, reference-update, freelance, academic, personal
-->

## Session Close

<!-- The closing ritual writes here. Three most impactful outputs of the session. -->

## Modified Reference Notes

<!-- Append-only list of canonical notes touched during the session. Example:
2026-01-15 10:15 [[infrastructure-notes]] updated: added deployment runbook
-->

## Open Items (Next Session)

<!-- Unfinished work, pending decisions, external replies awaited. These promote to the next session's handoff note. -->

## Links
- [[MOC]]
