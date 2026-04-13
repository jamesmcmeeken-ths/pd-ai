# Personal Development Repository

A structured knowledge base for tracking one-to-one meetings, goals, achievements, and professional growth — built to work with AI assistants like OpenCode.

## Purpose

This repository serves as:

- **Knowledge Base**: Searchable archive of one-to-one discussions and decisions
- **Progress Tracker**: Monitor growth and achievements over time
- **LLM-Ready Dataset**: Structured data for AI-powered insights and analysis
- **Performance Review Aid**: Evidence of contributions and development

## Repository Structure

```
pd/
├── README.md                          # This file
├── CONTEXT.md                         # Role, team, tech stack, company info
├── glossary.md                        # Terms, acronyms, project names
│
├── profile/                           # Stable personal characteristics
│   ├── README.md                      # Profile directory guide
│   ├── strengths.md                   # Strengths analysis (e.g., Clifton Strengths)
│   └── assessments/                   # Raw assessment data
│
├── goals/
│   ├── YYYY-annual.md                 # Year-level goals
│   ├── YYYY-q1.md                     # Q1 goals
│   └── YYYY-q2.md                     # Q2 goals
│
├── transcriptions/
│   ├── raw/                           # Original AI-generated transcriptions
│   └── YYYY-qX/                       # Structured summaries with YAML frontmatter
│
├── tracking/
│   ├── action-items.md                # Centralized action tracking
│   ├── achievements.md                # Wins and completed work
│   ├── feedback-log.md                # Manager feedback and growth areas
│   ├── topics-index.md                # Cross-reference of discussion topics
│   ├── timeline.md                    # Key dates and milestones
│   └── prep-notes/                    # Temporary prep notes (git ignored)
│
├── projects/
│   └── project-name.md                # Per-project tracking file
│
└── .templates/
    ├── meeting-summary-template.md    # Template for new meeting summaries
    ├── goal-template.md               # Template for goal documents
    ├── project-template.md            # Template for project tracking
    ├── prep-notes-template.md         # Template for 1-1 prep notes
    └── strengths-analysis-template.md # Template for strengths assessments
```

## Quick Start

### Getting Set Up

1. **Fill in `CONTEXT.md`** with your role, team structure, tech stack, and manager
2. **Fill in `glossary.md`** with terms, projects, and acronyms from your work
3. **Create your first goals file** using `.templates/goal-template.md`
4. **Add your profile** using `.templates/strengths-analysis-template.md`

### Adding a New Transcription

1. **Save raw transcription**: Place AI-generated notes in `transcriptions/raw/`
2. **Run the skill**: Ask OpenCode "process my meeting transcription" or `/skill process-meeting-transcription`
3. The skill will create a structured summary and update all tracking files automatically

### Creating Prep Notes for Meetings

1. Ask OpenCode "create prep notes for my 1:1" or `/skill create-prep-notes`
2. Reference prep notes during the meeting
3. After meeting: process the transcription, then prep notes are deleted automatically

## Using with OpenCode

This repository is configured with OpenCode skills for automated workflows:

```
/skill process-meeting-transcription   # After each 1:1
/skill create-prep-notes               # Before each 1:1
/skill quarterly-goal-transition       # At end of each quarter
/skill cross-referencing               # When linking documents
```

Or just describe what you need — OpenCode will load the right skill automatically.

### Recommended Prompts

**Progress Analysis**:
```
"Review my one-to-one transcriptions and tell me what progress I've made on [topic] over the last quarter"
```

**Goal Tracking**:
```
"Compare my Q1 goals with my achievements and action items. Am I on track?"
```

**Pattern Recognition**:
```
"What recurring themes appear in my feedback log? What patterns do you see?"
```

**Performance Review Preparation**:
```
"Help me prepare for my performance review by summarising my contributions"
```

**Strengths-Based Strategy**:
```
"Based on my strengths profile, how should I approach [specific challenge]?"
```

## Key Documents

- `CONTEXT.md` — Your role, team, tech stack
- `glossary.md` — Definitions of terms and projects
- `profile/strengths.md` — Your working style and talents
- `goals/YYYY-qX.md` — Current quarter goals
- `tracking/achievements.md` — Wins and evidence
- `tracking/feedback-log.md` — Manager feedback

## Maintenance

### Weekly (After Each One-to-One)
Use `/skill process-meeting-transcription` — it handles all of these:
- [ ] Save raw transcription
- [ ] Create structured summary
- [ ] Update action items, achievements, feedback, timeline, topics
- [ ] Update current quarter goals

### At Quarter End
Use `/skill quarterly-goal-transition` — it handles:
- [ ] Mark previous quarter complete
- [ ] Create new quarter goals
- [ ] Update CONTEXT.md and timeline

See `AGENTS.md` for full workflow documentation.
