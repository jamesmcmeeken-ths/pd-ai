---
name: cross-referencing
description: Establish bidirectional links between documents to maintain context and traceability. Use when creating or updating documents to ensure all cross-references are complete, accurate, and follow consistent patterns across meeting summaries, goals, projects, and tracking files.
---

# Cross-Referencing Patterns

Maintain clear connections between related documents so context is always accessible.

## Principle

Every document should link to related content. Links should be bidirectional when relevant — if A references B, then B should reference A (when it makes sense).

This prevents knowledge silos and ensures that someone reading any document can find related context.

## Patterns by Document Type

### Meeting Summaries → Everything

Meeting summaries should link outward to all related content:

**Link to related goals**:
```markdown
[Q1 YYYY Goals](../../goals/YYYY-q1.md)
```

**Link to projects** (if discussed):
```markdown
[Project Name](../../projects/project-name.md)
```

**Link to raw transcription** (source of truth):
```markdown
[Raw Transcription](../raw/YYYY-MM-DD-[participants]-raw.md)
```

**Link to previous/next meetings** (continuity):
```markdown
[Previous Meeting](./YYYY-MM-DD-summary.md) (2 weeks ago)
[Next Meeting](./YYYY-MM-DD-summary.md) (1 week later)
```

### Tracking Files → Source Meetings

Every entry in tracking files should trace back to where it came from:

**Action Items**:
```markdown
- [ ] Action item description
  - Source: [YYYY-MM-DD Meeting](../transcriptions/YYYY-qX/YYYY-MM-DD-summary.md)
  - Context: Why this action matters
```

**Achievements**:
```markdown
- **Shipped TICKET-123** — Brief impact statement. [Source: YYYY-MM-DD](../transcriptions/YYYY-qX/YYYY-MM-DD-summary.md)
```

**Feedback entries**:
```markdown
## YYYY-MM-DD Meeting

### Strengths
- [Quote or behavior observed]

### Development Areas
- [Area for growth with specific example]
```

**Timeline entries**:
```markdown
- ✅ Completed probation period ([Source](../transcriptions/YYYY-qX/YYYY-MM-DD-summary.md))
```

**Topics Index**:
```markdown
## Topic Area

- [YYYY-MM-DD](../transcriptions/YYYY-qX/YYYY-MM-DD-summary.md) — Brief description of what was discussed about this topic
```

### Goals → Meetings and Projects

Quarterly/annual goals should reference related evidence and work:

**Link to relevant meetings** (evidence of discussion):
```markdown
[YYYY-MM-DD Meeting](../transcriptions/YYYY-qX/YYYY-MM-DD-summary.md) discussed this goal
```

**Link to related projects**:
```markdown
[Project Name](../projects/project-name.md) is the primary vehicle for this goal
```

**Link to related tickets** (if discussed):
```markdown
Related tickets: TICKET-123, TICKET-124
```

### Projects → Meetings and Tickets

Project documents should show what's happening and where:

**Link to relevant meetings** (where decisions were made):
```markdown
Decision made in [YYYY-MM-DD Meeting](../transcriptions/YYYY-qX/YYYY-MM-DD-summary.md)
```

**Reference tickets** (implementation happening here):
```markdown
Implementation: TICKET-123, TICKET-124, TICKET-125
```

**Link to related goals** (strategic importance):
```markdown
Contributes to [QX YYYY Goals](../goals/YYYY-qX.md) — [Goal category]
```

## Bidirectional Linking

When two documents are closely related, link in both directions:

- Q1 goals → Q2 goals (next quarter)
- Q2 goals → Q1 goals (previous quarter)
- Meeting summary → Goal document
- Goal document → Meeting summary(ies) where it was discussed
- Project → Related meetings
- Meetings → Related projects
- Achievements → Source meetings
- Source meetings → Achievement tracking

**Example bidirectional pair**:

In `goals/YYYY-q1.md`:
```markdown
## Related Documents
- [Q2 YYYY Goals](./YYYY-q2.md) — Next quarter
- [YYYY-MM-DD Meeting](../transcriptions/YYYY-q1/YYYY-MM-DD-summary.md) — Progress review
```

In `goals/YYYY-q2.md`:
```markdown
## Related Documents
- [Q1 YYYY Goals](./YYYY-q1.md) — Previous quarter (COMPLETE)
```

In `transcriptions/YYYY-q1/YYYY-MM-DD-summary.md`:
```markdown
## Related Documents
- [Q1 YYYY Goals](../../goals/YYYY-q1.md) — On track
- [Q2 YYYY Goals](../../goals/YYYY-q2.md) — Planning begins
```

## Link Format

Use markdown relative links with clear labels:

```markdown
[Label text](relative/path/to/file.md)
```

**Good examples**:
```markdown
[YYYY-MM-DD Meeting](../transcriptions/YYYY-q1/YYYY-MM-DD-summary.md)
[Q1 YYYY Goals](../../goals/YYYY-q1.md)
[Project Name](../projects/project-name.md)
[Source: YYYY-MM-DD](../transcriptions/YYYY-q1/YYYY-MM-DD-summary.md)
```

**Bad examples**:
```markdown
[Click here](./YYYY-MM-DD-summary.md)  # Ambiguous label
[Meeting](../transcriptions/YYYY-q1/YYYY-MM-DD-summary.md)  # Too generic
YYYY-MM-DD (not a link at all)
```

## Consistency Checklist

When creating or updating a document, verify:

- [ ] **Meeting summaries** reference goals, projects, and raw transcription
- [ ] **Tracking files** (action-items, achievements, feedback-log, timeline, topics-index) link back to source meetings
- [ ] **Goals** link to related meetings where discussed
- [ ] **Projects** link to related meetings, goals, and tickets
- [ ] **Bidirectional links exist** for closely related documents (Q1 ↔ Q2 goals, etc.)
- [ ] **All links use relative paths** (not absolute)
- [ ] **Labels are descriptive** (what is this link? why follow it?)
- [ ] **Date format is consistent** (YYYY-MM-DD in links and filenames)

## When Cross-Referencing Occurs

- After creating a meeting summary → Link to goals, projects, action items
- When adding achievements/feedback → Link to source meeting
- When creating quarterly goals → Link to previous Q goals and relevant meetings
- When updating projects → Link to related meetings and goals
- When quarterly transition happens → Update bidirectional Q1 ↔ Q2 links
- When action items complete → Update action-items.md to reflect source meeting

## Anti-Patterns to Avoid

- **Orphaned documents**: Created but never linked from anywhere
- **Broken links**: Files moved but links not updated
- **Unidirectional when bidirectional needed**: Q1 goals link to Q2, but Q2 doesn't link back
- **Generic labels**: "See also" or "Related:" without specifics
- **Absolute paths**: Using `/Users/yourname/...` instead of relative paths
- **Over-linking**: Linking to tangentially related documents (adds noise, not clarity)

## Related Skills

- `process-meeting-transcription` — Creates meeting summaries that should have comprehensive cross-references
- `quarterly-goal-transition` — Updates cross-references during Q transitions
- `create-prep-notes` — Prep notes may reference previous related discussions
