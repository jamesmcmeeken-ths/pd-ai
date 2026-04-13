# Profile Directory

> Stable personal characteristics, strengths, and working style documentation

## Purpose

This directory contains information about your enduring personal attributes that inform your professional development but don't change frequently. Unlike the `/tracking` directory which captures time-bound events and progress, `/profile` contains baseline characteristics that help you understand:

- How you naturally work and think
- Your talents and potential blind spots
- Optimal strategies for leveraging your strengths
- How to interpret feedback through the lens of your personality

## Contents

- **[strengths.md](./strengths.md)** — Strengths assessment analysis and application to your current role
- **assessments/** — Raw assessment data and reports
- **reviews/** — Formal performance reviews

## Profile vs Tracking

### Profile (Stable)
- Personality assessments (Clifton Strengths, MBTI, etc.)
- Natural talents and working styles
- Core values and principles
- Long-term patterns across roles

### Tracking (Time-Bound)
- Meeting notes and transcriptions
- Quarterly goals and progress
- Feedback received in specific contexts
- Achievements and wins
- Action items and commitments

## How to Use with LLMs

Your profile data provides essential context for AI-powered insights. When working with an LLM:

### Loading Profile Context

For personalised advice, provide:
1. **Base context**: `CONTEXT.md` (role, team, company)
2. **Personal profile**: `profile/strengths.md` (how you work)
3. **Current state**: Relevant tracking files (what you're working on)
4. **Specific question**: What you need help with

### Example Prompts

**Strengths-Based Strategy**:
```
"Based on my strengths profile, how should I approach [specific challenge]?
What's the optimal strategy given my talents?"
```

**Feedback Interpretation**:
```
"Review this feedback through the lens of my strengths. Is this a blind spot
or overuse of a strength? How should I respond?"
```

**Task Alignment**:
```
"Which of these tasks align best with my strengths? Which will drain my energy
and require compensating strategies?"
```

**Career Planning**:
```
"What types of projects or roles would best leverage my strengths?
What should I delegate or avoid?"
```

## When to Update

### Add New Assessments
- When you take a new personality or strengths assessment
- Working style evaluations
- 360-degree feedback summaries
- Skills inventories

### Review Quarterly
- Update "Application to Current Role" section as goals shift
- Refresh cross-references to recent feedback and achievements
- Add new insights from self-reflection

### Annual Deep Dive
- Full review of all profile documents
- Update patterns and insights based on year of feedback
- Consider retaking assessments if available

## Related Documents

- [Context](../CONTEXT.md) — Role and team information
- [Feedback Log](../tracking/feedback-log.md) — External perspective on your work
- [Achievements](../tracking/achievements.md) — Evidence of strengths in action
