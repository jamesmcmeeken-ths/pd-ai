---
name: quarterly-goal-transition
description: Execute the end-of-quarter workflow to mark previous goals complete, create new quarterly goals, update context, and transition tracking systems. Use at quarter end (March 31, June 30, Sept 30, Dec 31) after the final one-to-one meeting is processed.
---

# Quarterly Goal Transition

Move from one quarter to the next by completing retrospective documentation, creating new goals, and updating all tracking systems.

## When to Use

- At the end of each quarter (March 31, June 30, Sept 30, Dec 31)
- **After** the final one-to-one meeting of the quarter has been processed using `process-meeting-transcription`
- When ready to formally transition to the new quarter

## The 6-Step Workflow

### Step 1: Mark Previous Quarter Complete

Open the previous quarter's goals file (e.g., `goals/YYYY-qN.md`).

Change the status from "In Progress" to "✅ COMPLETE":
```markdown
**Status**: ✅ **COMPLETE** - [Brief summary of what was achieved]  
**Last Updated**: YYYY-MM-DD
```

Add a final retrospective section with:
- What was achieved vs planned
- Key learnings
- What's carrying forward to next quarter
- Any unfinished work and why

### Step 2: Create New Quarter Goals Document

Create `goals/YYYY-qN.md` (e.g., `goals/2026-q3.md`).

Use `.templates/goal-template.md` as the starting point.

**Structure with these sections**:
- **Overview** (primary initiative, target impact, strategic focus area)
- **Monthly Breakdown** (Month 1, Month 2, Month 3 with specific objectives)
- **Project Impact Goals** (contributions to team initiatives)
- **Engineering Excellence Goals** (code quality, observability, efficiency improvements)
- **Direction & People Goals** (strategic contributions, mentorship, unblocking partners)
- **Success Metrics** (quantitative and qualitative measures)
- **Decision Points** (if applicable, e.g., development path choices, learning investments)

Make goals specific and tied to measurable outcomes. Avoid vague aspirations — each goal should be evaluable at quarter end.

### Step 3: Update Cross-References

**In the completed quarter goals** (`goals/YYYY-qX.md` — previous):

Add a link to the next quarter:
```markdown
## Related Documents
- [Next Quarter Goals](./YYYY-q(X+1).md) — Q(X+1) YYYY
- [Previous Quarter Goals](./YYYY-q(X-1).md) — Q(X-1) YYYY (COMPLETE)
```

**In the new quarter goals** (`goals/YYYY-qX.md` — current):

Add a link to the previous quarter:
```markdown
## Related Documents
- [Previous Quarter Goals](./YYYY-q(X-1).md) — Q(X-1) YYYY (COMPLETE)
```

**Update annual goals** (`goals/YYYY-annual.md`):

Add a section for the new quarter reflecting its focus, and mark previous quarter sections complete.

### Step 4: Update CONTEXT.md

This is a major update. Modify these sections:

**Progress Snapshot**:
- Add a "QX Summary" section with key achievements
- Include a table of completed tickets/shipped features
- Note major milestones reached
- Remove old quarter sections or move to archive

**Current Focus Areas**:
- Mark completed Q initiatives with ✅
- Add new Q priorities
- Update any development path decisions or focus shifts

**In-Flight Work**:
- Update ticket statuses
- Remove completed items
- Add new initiatives starting in new quarter

**Team & Structure**:
- Note any personnel transitions (if any occurred)
- Update role clarity if responsibilities shifted

**Milestone Status**:
- Update probation status, anniversaries, or other time-based milestones

### Step 5: Update Timeline

Open `tracking/timeline.md`.

- **Add quarter end date**: e.g., "Q(N) YYYY Complete ✅"
- **Create new quarter section**: Add the new quarter heading with its major initiatives
- **Mark completed milestones** with ✅
- **Add upcoming Q milestones** to the "Upcoming" section at the bottom
- **Add context**: Brief description of what happened (1-2 sentences per milestone)

### Step 6: Archive and Clean Up

**Delete prep notes**:
- Remove all files from `tracking/prep-notes/` folder
- Prep notes are temporary staging — they're no longer needed once meetings are processed

**Review action items** (`tracking/action-items.md`):
- Mark completed Q items as done (move to "Completed" section)
- Carry forward active items that span multiple quarters
- Remove stale/obsolete items that are no longer relevant
- Add any new Q priorities as action items

**Review feedback patterns** (`tracking/feedback-log.md`):
- Add a "Quarterly Patterns" summary noting recurring themes in strengths or growth areas
- This becomes valuable input for annual reviews and goal-setting for next Q

## Key Principles

- **Sequence matters**: Complete steps in order. Step 1 informs Step 2, which informs Steps 3-6.
- **Retrospective before looking forward**: Articulate what happened last Q before planning the next one.
- **Bidirectional links**: Previous Q ↔ Current Q ↔ Next Q (when it exists).
- **Clean state**: Remove stale prep notes and action items so tracking stays clean.
- **Evidence-based**: Ground new quarter goals in achievements and feedback from previous quarter.

## Typical Timeline

```
Quarter Ends (e.g., March 31, June 30)
    ↓
Final meeting of the quarter processed (process-meeting-transcription)
    ↓
Run quarterly-goal-transition skill
    ↓
Step 1: Mark previous quarter complete
Step 2: Create new quarter goals
Step 3: Cross-reference Q(N) ↔ Q(N+1)
Step 4: Update CONTEXT.md
Step 5: Update tracking/timeline.md
Step 6: Clean up prep notes & action items
    ↓
Ready for the new quarter
```

## Output

Successfully completing this workflow produces:
- Previous quarter marked complete with retrospective
- New quarterly goals document created and linked
- CONTEXT.md reflects new Q focus and progress
- Timeline updated with Q transitions
- Tracking files cleaned (stale items removed, active items carried forward)
- Prep notes archived
- All documents cross-referenced

## Related Skills

- `process-meeting-transcription` — Should be run on final meeting before this skill
- `create-prep-notes` — For next Q meeting preparation
