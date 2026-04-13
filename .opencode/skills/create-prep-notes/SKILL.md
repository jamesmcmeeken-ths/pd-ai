---
name: create-prep-notes
description: Prepare structured notes for upcoming one-to-one meetings with your manager. Use 1-2 days before the meeting to organize discussion topics, progress updates, questions, and required guidance. Delete prep notes after the meeting is processed.
---

# Create Prep Notes

Organize your thoughts before one-to-one meetings to make the most of limited discussion time.

## When to Use

- **1-2 days before** each one-to-one meeting with your manager
- When you want a structured approach to discussing progress, blockers, and strategic topics
- Prep notes are temporary — they'll be deleted after the meeting is processed

## The Process

### Before the Meeting (1-2 Days Prior)

**Create the file**: `tracking/prep-notes/1-1-prep-YYYY-MM-DD.md`

Use the template from `.templates/prep-notes-template.md`.

**Fill in these sections**:

1. **Progress Update** (1-2 minutes)
   - Tickets completed since last meeting
   - Major milestones reached
   - Blockers encountered
   - Keep it brief — just headlines, not detailed descriptions

2. **Main Topics** (15-20 minutes)
   - 2-3 key discussion points with time allocations
   - For each topic: what's the context, what decision/guidance do you need?
   - Use these to drive focused discussion
   - Example: "Migration strategy (8 min) — Framework choice, rollout sequencing, risk assessment"

3. **Questions for Manager** (3-5 minutes)
   - Specific, actionable questions
   - Not vague — each question should have a clear, answerable response
   - Examples: "Should we prioritize observability before the migration?" or "How do I approach unblocking the design team?"

4. **Quick Items** (1-2 minutes)
   - Non-critical updates or FYIs
   - Things that don't need discussion but are good for context
   - Personal/professional updates if relevant

5. **What You Need From Manager**
   - Feedback on specific decisions or approaches
   - Unblocking from cross-functional dependencies
   - Direction on strategic priorities
   - Be explicit about what would help

**Before the meeting**, also:
- Review previous action items (from `tracking/action-items.md`)
- Check recent achievements to reference if relevant
- Read latest meeting summary to remember context

### During the Meeting

- Reference your prep notes for structure
- Take additional notes if the conversation goes deeper than expected
- Or rely on an AI transcription tool if available — prep notes are mainly for your organization

### After the Meeting

1. **Process the transcription** using the `process-meeting-transcription` skill
2. **Delete prep notes** from `tracking/prep-notes/` folder immediately after processing
3. The structured meeting summary becomes the permanent record — prep notes are temporary

## Why Prep Notes Are Separate & Temporary

- **Temporary staging**: They help you organize thoughts before the meeting
- **Git ignored**: The `tracking/prep-notes/` folder is in `.gitignore` — these don't get committed
- **Delete after processing**: Once the meeting summary is created, prep notes are redundant
- **Not archival**: The structured meeting summary (`transcriptions/YYYY-qX/YYYY-MM-DD-summary.md`) is the permanent record

This keeps prep files from cluttering version control and removes the temptation to reference old prep notes instead of the actual meeting record.

## File Format

```markdown
# 1:1 Prep — YYYY-MM-DD

## Progress Update
- ✅ Shipped TICKET-123
- 🚀 Started homepage redesign
- 🚧 Blocked on API latency investigation

## Main Topics

### Topic 1: [Topic Name] (X min)
- Context: [Brief background]
- Question/Need: [What you want to discuss or decide]

### Topic 2: [Topic Name] (X min)
- Context: [Brief background]
- Question/Need: [What you want to discuss or decide]

### Topic 3: [Topic Name] (X min)
- Context: [Brief background]
- Question/Need: [What you want to discuss or decide]

## Questions for Manager
- [Specific question 1?]
- [Specific question 2?]
- [Specific question 3?]

## Quick Items
- [FYI or quick update]
- [Personal/professional context if relevant]

## What I Need From Manager
- [Specific feedback, unblocking, or direction]
```

## Key Principles

- **Specificity matters**: Vague prep notes are less useful. Be concrete about topics, questions, and what you need.
- **Time allocation**: Roughly allocate minutes to each topic so you pace the conversation.
- **Action-oriented**: Each topic should have a clear reason it's on the agenda (decision needed, feedback wanted, etc.).
- **Review before writing**: Check action items and recent achievements so you reference them naturally in the meeting.
- **Delete after processing**: This keeps the repo clean and prevents confusion between prep (temporary) and meeting record (permanent).

## Output

Successfully creating prep notes produces:
- 1 structured prep notes file in `tracking/prep-notes/`
- Clear agenda organized by topic with time allocations
- Specific questions ready to ask
- Permanent record (meeting summary) created after meeting is processed
- Prep notes file deleted after processing

## Related Skills

- `process-meeting-transcription` — Processes the meeting into permanent record; delete prep notes after this completes
- `quarterly-goal-transition` — Happens at quarter end after multiple meetings processed
