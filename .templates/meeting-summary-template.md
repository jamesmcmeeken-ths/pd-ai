---
date: YYYY-MM-DD
attendees: [Your Name, Manager Name, ...]
topics: [topic-1, topic-2, topic-3]
projects: [project-name-1, project-name-2]
action_items: N
key_decisions: [decision-1, decision-2]
quarter: QX-YYYY
meeting_type: weekly-one-on-one | goal-setting | performance-review | ad-hoc
---

# Meeting Summary: YYYY-MM-DD

## Key Themes
- **Theme 1**: Brief description
- **Theme 2**: Brief description
- **Theme 3**: Brief description

## Main Discussion Points

### Topic 1
**Context**: Background information

**Discussion**:
- Main point 1
- Main point 2
- Main point 3

**Outcomes**:
- Result or decision 1
- Result or decision 2

### Topic 2
**Context**: Background information

**Discussion**:
- Main point 1
- Main point 2

**Outcomes**:
- Result or decision

## Outcomes & Agreements
- Agreement or commitment 1
- Agreement or commitment 2
- Agreement or commitment 3

## Action Items
- [ ] Person: Task description (Due: YYYY-MM-DD)
  - Additional context if needed
- [ ] Person: Task description (Due: YYYY-MM-DD)

## Related Documents
- [Q1 YYYY Goals](../../goals/YYYY-q1.md)
- [Project Name](../../projects/project-name.md)
- [Raw Transcription](../raw/YYYY-MM-DD-you-manager-raw.md)

---

## Notes for Writing Summaries

### YAML Frontmatter
- **date**: Meeting date in YYYY-MM-DD format
- **attendees**: List of attendee names
- **topics**: Main themes discussed (kebab-case)
- **projects**: Related projects being worked on
- **action_items**: Number of action items from meeting
- **key_decisions**: Important decisions or agreements made
- **quarter**: Which quarter (e.g., Q1-2026)
- **meeting_type**: Type of meeting

### Structure Guidelines
1. **Key Themes**: 3-5 bullet points capturing main themes
2. **Main Discussion Points**: Detailed sections for each major topic
   - Use context, discussion, outcomes structure
   - Include specific examples and decisions
3. **Outcomes & Agreements**: Clear list of what was agreed
4. **Action Items**: Specific, actionable tasks with owners and due dates
5. **Related Documents**: Links to goals, projects, raw transcription

### Tips
- Keep summaries focused on salient points
- Include enough detail for context but avoid verbatim transcription
- Link to related documents for additional context
- Use quotes for particularly important statements
- Mark action items with clear ownership and deadlines
- Reference line numbers from raw transcription if useful

### Cross-Referencing
After creating summary:
1. Add action items to `tracking/action-items.md`
2. Update `tracking/topics-index.md` with topics discussed
3. Update relevant project files in `projects/`
4. Add achievements to `tracking/achievements.md` if applicable
5. Log feedback in `tracking/feedback-log.md` if received
6. Update `tracking/timeline.md` if milestones discussed
