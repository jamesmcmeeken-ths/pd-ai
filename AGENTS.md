# AI Instructions for Personal Development Repository

> **Important Note for AI Assistants**: Use the acronym **DRI** (Directly Responsible Individual), not "DRRi". The correct term is DRI throughout all documentation. See [glossary.md](./glossary.md) for definition.

## Repository Purpose

This repository serves as a structured knowledge base for professional development tracking. It contains:
- One-to-one meeting transcriptions and summaries
- Quarterly and annual goals
- Professional achievements and feedback
- Action items and project tracking
- Personal profile (Clifton Strengths)

The repository is designed to be **LLM-friendly** with structured data, YAML frontmatter, and cross-referenced documents.

## Core Principles

1. **Consistency**: All documents follow established templates and patterns
2. **Cross-referencing**: Documents link to related content for context
3. **Temporal organization**: Content organized by quarter and date
4. **Separation of concerns**: Stable profile data vs time-bound tracking data
5. **Evidence-based**: Concrete achievements and feedback over generalizations
6. **Progression-aware**: Goals and achievements are framed with awareness of your current → target level progression gap

---

## Career Progression Framework

**Current level**: [Your Current Level, e.g. Senior Engineer I]
**Target level**: [Your Target Level, e.g. Senior Engineer II]
**Framework location**: `profile/progression/`

### Files

- `profile/progression/[current-level].md` — Full competency criteria for the current level
- `profile/progression/[target-level].md` — Full competency criteria for the target level
- `profile/progression/progression-gap-analysis.md` — Side-by-side gap analysis with current standing, quarterly goal mapping, and decision-making questions

### How the framework is used

The progression framework is a **background lens**, not a primary target. It should:

- **Inform goal prioritisation**: When evaluating whether to pursue a goal or take on extra work, check whether it addresses a genuine gap at the next level
- **Shape how achievements are framed**: Achievements should be described using language that reflects target-level behaviours where applicable (e.g., "created opportunities for others", "communicated long-term vision", "led cross-org adoption")
- **Guide meeting prep**: When preparing for 1:1s with your manager, reference the gap analysis to ensure discussion topics are progression-relevant
- **Not override authenticity**: Don't chase the framework at the expense of genuine growth. Trust that doing good work in the right areas gets you there naturally

### The core behavioural shift (typical SE I → SE II example)

> Current level: "I lead projects well and communicate within my squad and guild."
> Target level: "I make the people and systems around me better, and communicate the long-term vision beyond my team."

### Key questions when evaluating work

1. **Does this create opportunities for others?** (Initiative marker)
2. **Does this build a cross-discipline strategic relationship?** (Leadership marker)
3. **Can this be framed around long-term vision, not just immediate output?** (Communication marker)
4. **Does this involve leading something org-wide, not just squad-wide?** (AI/Technical effectiveness marker)

### When processing meetings or updating goals

When running the `process-meeting-transcription` skill or reviewing goals:

1. **Check achievements against gap analysis**: Can any achievement be framed in target-level language? (e.g., "cross-functional influence", "creates opportunities for others", "communicates vision")
2. **Flag new progression evidence**: If a new behaviour or piece of work clearly demonstrates a target-level competency, note it in the feedback log and achievements
3. **Weigh new action items**: If a new action item emerges, consider whether it addresses a gap or reinforces an already-strong area. Prefer the former when choices exist

---

## Skills-Based Workflows

This repository uses **OpenCode skills** to automate and standardize common workflows. Instead of manual checklists, workflows are encapsulated as reusable skills that can be triggered via command or natural language.

### How to Use Skills

**From OpenCode terminal:**
```
/skill skill-name
```

**Or ask naturally:**
Ask OpenCode to help with the task (e.g., "I need to process my meeting notes") and it will automatically load the relevant skill.

**Skills available:**
- `process-meeting-transcription` — Process raw meeting transcriptions
- `quarterly-goal-transition` — Execute quarter-end transitions
- `create-prep-notes` — Prepare meeting prep notes
- `cross-referencing` — Establish document cross-references

All skills live in `.opencode/skills/` and are automatically discovered by OpenCode.

---

## Common Workflows

### 1. Processing Meeting Transcriptions

**→ Use the `process-meeting-transcription` skill**

After each one-to-one meeting with your manager, when a raw transcription is available:

```
/skill process-meeting-transcription
```

Or ask naturally: "I need to process my meeting notes from [manager name]"

**What it does**: Converts raw transcriptions into structured summaries with cross-references, action items, achievements, and feedback tracking. Completes an 8-step workflow that integrates the meeting into all tracking systems.

**Input**: Raw transcription in `transcriptions/raw/YYYY-MM-DD-[you]-[manager]-raw.md`

**Output**: 
- 1 new structured meeting summary (with YAML frontmatter)
- 7 updated tracking files (action-items, achievements, feedback-log, timeline, topics-index, goals, CONTEXT)
- All documents cross-referenced

**For detailed step-by-step instructions**: See `.opencode/skills/process-meeting-transcription/SKILL.md`

---

### 2. Quarterly Goal Transitions

**→ Use the `quarterly-goal-transition` skill**

At the end of each quarter (March 31, June 30, Sept 30, Dec 31), after the final one-to-one meeting is processed:

```
/skill quarterly-goal-transition
```

Or ask naturally: "I need to transition to the next quarter"

**What it does**: Executes the end-of-quarter workflow — marks previous goals complete, creates new quarterly goals, updates tracking systems (CONTEXT.md, timeline, action items), and prepares for the next quarter.

**When to use**: 
- Final one-to-one meeting of the quarter must already be processed using `process-meeting-transcription`
- Ready to formally transition to the new quarter

**Output**:
- Previous quarter marked complete with retrospective
- New quarterly goals created and linked
- CONTEXT.md reflects new Q focus and progress
- Timeline updated with Q transitions
- Prep notes cleaned up
- All tracking files synchronized

**For detailed step-by-step instructions**: See `.opencode/skills/quarterly-goal-transition/SKILL.md`

---

### 3. Creating and Managing Prep Notes

**→ Use the `create-prep-notes` skill**

Before each one-to-one meeting:

```
/skill create-prep-notes
```

Or ask naturally: "I need to prepare for my 1:1 with [manager name]"

**What it does**: Helps you organize discussion topics, progress updates, questions, and required guidance into structured prep notes. Prep notes are temporary — deleted after the meeting is processed.

**When to use**: 1-2 days before each one-to-one meeting

**Output**:
- Prep notes created in `tracking/prep-notes/1-1-prep-YYYY-MM-DD.md`
- Clear agenda organized by topic with time allocations
- Specific questions ready to ask
- Permanent meeting record (summary) created after meeting is processed
- Prep notes file deleted after processing

**For detailed instructions**: See `.opencode/skills/create-prep-notes/SKILL.md`

---

### 4. Cross-Referencing Patterns

**→ Use the `cross-referencing` skill**

When linking or cross-referencing documents:

```
/skill cross-referencing
```

Or ask naturally: "I need to link these documents" or "Let me review cross-referencing patterns"

**What it does**: Establishes and maintains bidirectional links between documents to ensure context is always accessible and traceability is complete.

**When to use**: 
- While creating meeting summaries (to link to goals, projects, action items)
- When adding achievements or feedback (to link to source meetings)
- When creating quarterly goals (to link to previous quarters and related meetings)
- When updating projects (to link to related meetings and goals)
- During quarterly transitions (to update bidirectional Q1 ↔ Q2 links)

**Key principles**:
- Every document should link to related content
- Links should be bidirectional when relevant (A → B and B → A)
- Use relative markdown links with descriptive labels
- Always include source attribution in tracking files

**For detailed patterns and examples**: See `.opencode/skills/cross-referencing/SKILL.md`

---

## File Update Checklist

These checklists are now automated via skills. Use them for reference if manually reviewing work:

### After Every Meeting
Use the `process-meeting-transcription` skill to complete all of these in sequence:
- [ ] `transcriptions/YYYY-qX/YYYY-MM-DD-summary.md` — Create structured summary
- [ ] `tracking/action-items.md` — Add new, complete old, remove stale
- [ ] `tracking/achievements.md` — Add new wins and contributions
- [ ] `tracking/feedback-log.md` — Log feedback and patterns
- [ ] `tracking/timeline.md` — Add key dates and milestones
- [ ] `tracking/topics-index.md` — Cross-reference topics discussed
- [ ] `CONTEXT.md` — Update if focus/priorities/team changed
- [ ] `goals/YYYY-qX.md` — Update current quarter progress

### At Quarter End (Every 3 Months)
Use the `quarterly-goal-transition` skill to complete all of these in sequence:
- [ ] `goals/YYYY-qX.md` (previous) — Mark complete with summary
- [ ] `goals/YYYY-qX.md` (new) — Create next quarter goals
- [ ] `goals/YYYY-annual.md` — Update with quarterly progress
- [ ] `CONTEXT.md` — Major update with quarter summary
- [ ] `tracking/timeline.md` — Add quarter section, mark milestones complete
- [ ] `tracking/feedback-log.md` — Add quarterly patterns summary
- [ ] `tracking/action-items.md` — Archive completed, carry forward active
- [ ] `tracking/prep-notes/` — Clean up any old prep notes

### Monthly (After ~4 meetings)
Use skills as needed after completing meetings:
- [ ] `tracking/achievements.md` — Review and ensure all wins captured
- [ ] `tracking/timeline.md` — Add monthly milestones
- [ ] `goals/YYYY-qX.md` — Check progress on monthly targets

---

## Best Practices

### Writing Meeting Summaries
1. **Lead with themes**: 3-5 key themes in bullet points
2. **Organize by topic**: Group related discussion points together
3. **Include context**: Explain why decisions matter
4. **Quote important phrases**: Capture exact feedback when meaningful
5. **Link liberally**: Cross-reference related documents
6. **Action items clarity**: Who, what, why for each action

### Managing Action Items
1. **Active items on top**: Keep "Active" section first
2. **Context is key**: Explain why each action matters
3. **Source everything**: Link to meeting where item originated
4. **Complete promptly**: Move to "Completed" as soon as done
5. **Remove stale items**: Don't let list grow indefinitely

### Tracking Achievements
1. **Specificity matters**: "Shipped TICKET-123" not "Made progress"
2. **Include impact**: Why it matters, what it enables
3. **Link to evidence**: Reference meeting summaries, PRs, tickets
4. **Organize by theme**: Technical, Leadership, AI, Relationships
5. **Use dates**: Timestamp when achievement occurred

### Maintaining Consistency
1. **Follow templates**: Use `.templates/` files as starting point
2. **Date format**: Always YYYY-MM-DD
3. **File naming**: Lowercase with dashes (e.g., `2026-q1.md`)
4. **YAML frontmatter**: Always include in meeting summaries
5. **Cross-reference**: Link documents bidirectionally

### Working with LLMs
1. **Load context first**: Provide CONTEXT.md, profile/strengths.md, glossary.md
2. **Be specific**: Reference exact documents and sections
3. **Request structured output**: Ask for YAML, tables, organized sections
4. **Verify facts**: AI should reference actual documents, not invent
5. **Use this file**: Point AI to `AGENTS.md` for workflows

---

## Document Templates

All templates are in `.templates/` directory:

- `meeting-summary-template.md` — For processing transcriptions
- `goal-template.md` — For quarterly/annual goals
- `project-template.md` — For tracking major initiatives
- `prep-notes-template.md` — For one-to-one meeting preparation
- `strengths-analysis-template.md` — For personality assessments

When creating new documents, always start with the appropriate template.

---

## Special Folders

### `tracking/prep-notes/` (Temporary, Git Ignored)
- **Purpose**: Staging area for meeting preparation
- **Lifecycle**: Create before meeting → Delete after processing
- **Git ignored**: Yes (in `.gitignore`)
- **Contents**: 1-1 prep notes only
- **Cleanup**: Delete files after meeting summary created

### `transcriptions/raw/` (Permanent, Git Tracked)
- **Purpose**: Original AI-generated transcriptions
- **Lifecycle**: Create → Keep forever
- **Git tracked**: Yes
- **Contents**: Raw meeting notes from your transcription tool
- **Cleanup**: Never delete (source of truth)

### `transcriptions/YYYY-qX/` (Permanent, Git Tracked)
- **Purpose**: Structured meeting summaries with YAML frontmatter
- **Lifecycle**: Create → Keep forever
- **Git tracked**: Yes
- **Contents**: Processed, organized meeting summaries
- **Cleanup**: Never delete (primary reference)

---

## Performance Calibration Axes

Goals and achievements should be tracked across four axes:

1. **Project Impact**: Direct contributions toward team goals (e.g., key initiatives, shipped features)
2. **Engineering Excellence**: Code quality, observability, helping teams move faster
3. **Direction**: Setting priorities, unblocking cross-functional partners, strategic contributions
4. **People**: Mentorship, guidance, helping others achieve more through knowledge sharing

When documenting achievements, consider which axis they demonstrate.

---

## Questions or Issues?

If workflows need clarification or skills need updating:
1. Review the skill in `.opencode/skills/<skill-name>/SKILL.md` for detailed instructions
2. Update the skill if patterns change
3. Update this file (`AGENTS.md`) with high-level changes
4. Update relevant template in `.templates/` folder if applicable
5. Add new terms to `glossary.md` if needed
6. Ensure cross-references remain consistent

This is a living document — update it and the skills as workflows evolve.
