---
name: process-meeting-transcription
description: Process raw meeting transcriptions into structured summaries with cross-references, action items, achievements, and feedback tracking. Use after each one-to-one meeting when a raw transcription is available. Ensure all 8 workflow steps are completed and documents are cross-referenced.
---

# Process Meeting Transcription

Convert raw meeting transcriptions into structured, cross-referenced documentation. This workflow has 8 sequential steps that integrate with the repo's tracking system.

## When to Use

- After each one-to-one meeting with your manager
- When you have a raw transcription (from an AI transcription tool, Google Meet, or similar)
- The raw transcription file (however it was originally named) should be in `transcriptions/raw/`

## The 8-Step Workflow

### Step 0: Rename the Raw Transcription File

AI transcription tools (e.g., Gemini, Otter, Fireflies) produce files with non-standard names like `Alex _ Jordan – 2026_04_09 13_25 BST – Notes by Gemini.md`. Rename it to follow the repo convention before proceeding.

**Convention**: `YYYY-MM-DD-[participants]-raw.md`

**Examples**:
```
Alex _ Jordan – 2026_04_09 13_25 BST – Notes by Gemini.md
→ 2026-04-09-alex-jordan-raw.md

Meeting with Sarah 2026-07-15.md
→ 2026-07-15-alex-sarah-raw.md
```

**Rules**:
- Date first, in `YYYY-MM-DD` format (extracted from the filename or file content)
- Participant names in lowercase, hyphen-separated, alphabetical or natural order
- Always ends in `-raw.md`
- Stored in `transcriptions/raw/`

Rename the file now before moving to Step 1.

### Step 1: Create Structured Summary

Create a new file: `transcriptions/YYYY-qX/YYYY-MM-DD-summary.md`

Use the template from `.templates/meeting-summary-template.md` as a starting point.

**Add YAML frontmatter** with these fields:
```yaml
---
date: YYYY-MM-DD
attendees: [Your Name, Manager Name]
topics: [topic-1, topic-2, topic-3]
projects: [project-1, project-2]
action_items: N
key_decisions: [decision-1, decision-2]
quarter: QX-YYYY
meeting_type: weekly-one-on-one
---
```

**Structure the content** with these sections:
- **Key Themes** (3-5 bullets capturing the main discussion patterns)
- **Main Discussion Points** (organized by topic, not chronologically)
- **Outcomes & Agreements** (specific commitments or decisions made)
- **Action Items** (with assignee and context for each)
- **Related Documents** (cross-references to goals, projects, other meetings)

The summary should be readable independently — someone should understand the meeting without reading the raw transcript.

### Step 2: Update `tracking/action-items.md`

- **Add new action items** from the meeting to the "Active" section
- **Move completed items** from "Active" to "Completed" section
- **Remove outdated items** no longer relevant
- **Use this format**:
  ```markdown
  - [ ] Action item description
    - Source: [YYYY-MM-DD Meeting](../transcriptions/YYYY-qX/YYYY-MM-DD-summary.md)
    - Context: Why this matters and what it enables
  ```

Keep the "Active" section at the top. Always link back to the source meeting.

### Step 3: Update `tracking/achievements.md`

- **Add new achievements** to the appropriate month section
- **Organize by category**:
  - Technical Contributions
  - Leadership & Influence
  - AI & Innovation
  - Relationship Building
- **Include impact**: What was achieved and why it matters (not just what was done)
- **Link to source**: Reference the meeting summary where this was discussed

Example:
```markdown
- **Shipped TICKET-123: Feature Name** — Brief impact statement explaining what this enables. [Source: YYYY-MM-DD](../transcriptions/YYYY-qX/YYYY-MM-DD-summary.md)
```

### Step 4: Update `tracking/feedback-log.md`

- **Add a new section** with the meeting date as the heading
- **Categorize feedback** under:
  - Positive feedback (strengths demonstrated)
  - Development areas (growth opportunities)
  - Specific examples (concrete behaviors)
- **Update the patterns section** at the top: Note any recurring themes in strengths or areas for growth
- **Quote meaningful feedback**: Capture exact phrasing when it's actionable

### Step 5: Update `tracking/timeline.md`

- **Add key dates** to the appropriate monthly section
- **Mark milestones complete** with ✅ when achieved
- **Update "In Progress" and "Upcoming"** sections
- **Add brief context**: What happened, why it matters

Example:
```markdown
### Month YYYY

- ✅ Completed probation period — Positive review and transition to open-ended role
- 🚀 Started QX goals — Focus on [primary initiative]
```

### Step 6: Update `tracking/topics-index.md`

- **Add the meeting reference** under relevant topic headings
- **Create new topic sections** if discussing new themes not covered before
- **Include a 1-2 sentence summary** of what was discussed about this topic
- **Maintain alphabetical order** within each section

Example:
```markdown
## AI & LLM Integration

- [YYYY-MM-DD](../transcriptions/YYYY-qX/YYYY-MM-DD-summary.md) — Discussion of prompt engineering patterns and when to use few-shot vs zero-shot approaches for different domains.
```

### Step 7: Update `CONTEXT.md`

- **Update "Current Focus Areas"** if priorities shifted
- **Update "Progress Snapshot"** with latest achievements
- **Update "In-Flight Work"** with current ticket status (if discussed)
- **Update team structure** if personnel changes occurred
- **Update probation/milestone status** if applicable

### Step 8: Update or Create Goal Documents

- **If quarterly transition**: Create new `goals/YYYY-qX.md` using `.templates/goal-template.md` and mark previous quarter complete
- **If mid-quarter**: Update current quarter goals (`goals/YYYY-qX.md`) with progress toward objectives
- **Add cross-references**: Link from meeting summary to relevant goals, and from goals back to this meeting

## Key Principles

- **Sequence matters**: Do steps in order. Step 1 (summary) informs all subsequent steps.
- **Cross-reference everything**: Every entry in tracking files should link back to source meetings. Every meeting should link to related goals/projects.
- **Evidence-based**: Achievements should be specific and tied to outcomes, not activities.
- **Clean up as you go**: Remove stale action items rather than letting them accumulate.
- **Use exact dates**: Always YYYY-MM-DD format for consistency.
- **Progression lens**: After completing steps 3–4 (achievements and feedback), check `profile/progression/progression-gap-analysis.md`. Ask: Can any achievement be framed in target-level language? Does any new action item address a genuine gap? Note progression evidence in the feedback log where relevant.

## Output

Successfully completing this workflow produces:
- 1 new structured meeting summary (with YAML frontmatter)
- 7 updated tracking files (action-items, achievements, feedback-log, timeline, topics-index, goals, CONTEXT)
- All documents cross-referenced with explicit links
- Ready for the next meeting or quarterly review

## Related Skills

- `quarterly-goal-transition` — For handling quarter-end transitions
- `cross-referencing` — For linking patterns and best practices
