# Annual Plan Template

Use this template when generating annual planning documents.

**IMPORTANT: For document generation, use Bash heredoc method (see SKILL.md Method 1)**
- This template is ~200 lines, which is too long for Write tool
- **Generate ALL sections in ONE Bash call using { } braces**
- **This ensures only ONE user confirmation is needed (not 7 confirmations)**
- See SKILL.md "Document Generation Process" for detailed instructions

**Batch Execution Format:**
```bash
{
  cat > file.md << 'EOF'
Section 0
EOF

  cat >> file.md << 'EOF'
Section 1
EOF

  # ... all sections
} && echo "✓ Done"
```

## Document Structure & Section Boundaries

The document should be generated in these sections:

### Section 0: Header (lines 1-10)
- Title, date, theme word

### Section 1: Reality Check (lines 11-40)
- I. Reality Check & Role Confirmation

### Section 2: Life Wheel (lines 41-70)
- II. Life Wheel Structural Assessment

### Section 3: Strategic Focus (lines 71-100)
- III. Annual Strategic Positioning

### Section 4: OKR (lines 101-130)
- IV. Annual OKRs

### Section 5: Action System & Routine (lines 131-200)
- V. Action System Design
- V (Appendix). Daily Routine Schedule
- VI. Recovery & Input Budget

### Section 6: 12-Week Rhythm & Calendar (lines 201-end)
- VII. 12-Week Rhythm Planning
- Appendix: Annual Calendar View

---

## Full Template Content

```markdown
# {Year} Annual Strategic Map

> Generated: {date}
> Annual Theme: {theme_word}

---

## I. Reality Check & Role Confirmation

### Current Life Roles
- {role_1}
- {role_2}
- ...

### Hard Constraints
| Constraint Type | Description | Impact Level |
|----------------|-------------|--------------|
| {type} | {description} | High/Medium/Low |

### Annual Subtraction List (Things to reduce/stop)
1. {item_1}
2. {item_2}
3. {item_3}

> This year's key is not working harder, but making fewer mistakes.

---

## II. Life Wheel Structural Assessment

### Eight Dimensions Scoring (1-10)

| Dimension | Score | Status | Notes |
|-----------|-------|--------|-------|
| Health | {score} | {normal/danger zone/overdrawn} | {note} |
| Career/Studies | {score} | | |
| Wealth/Financial Security | {score} | | |
| Family | {score} | | |
| Intimate Relationships | {score} | | |
| Social/Friends | {score} | | |
| Personal Growth | {score} | | |
| Leisure/Recovery | {score} | | |

### Structural Risk Assessment
- **Danger Zone**: {dimension} - {reason}
- **Overdrawn High Score**: {dimension} - {reason}
- **Systemic Risk**: {risk_description}

---

## III. Annual Strategic Positioning

### Annual Positioning Statement
> {1-3 sentences positioning statement}

### Battlefield Allocation

| Type | Dimension | Strategy |
|------|-----------|----------|
| Main Battlefield | {dimension_1} | {strategy} |
| Main Battlefield | {dimension_2} | {strategy} |
| 60-Point Strategy | {dimension} | {approach} |
| Do Not Optimize | {dimension} | {reason} |

### Annual Success Criteria (At least 2 achieved = Success)
1. {criterion_1} - Verification: {evidence}
2. {criterion_2} - Verification: {evidence}
3. {criterion_3} - Verification: {evidence}

---

## IV. Annual OKRs (By Main Battlefield)

### Main Battlefield 1: {dimension_name}

**Objective**: {state_change_description}

| Key Result | Verification | 12-Week Milestones |
|------------|--------------|-------------------|
| KR1: {measurable_result} | {evidence} | Q1: / Q2: / Q3: / Q4: |
| KR2: {measurable_result} | {evidence} | Q1: / Q2: / Q3: / Q4: |
| KR3: {measurable_result} | {evidence} | Q1: / Q2: / Q3: / Q4: |

### Main Battlefield 2: {dimension_name}

**Objective**: {state_change_description}

| Key Result | Verification | 12-Week Milestones |
|------------|--------------|-------------------|
| KR1: {measurable_result} | {evidence} | |
| KR2: {measurable_result} | {evidence} | |

---

## V. Action System Design

### KR: {kr_name}

| Element | Content |
|---------|---------|
| **Minimum Action** | {5-20 minute low-barrier action} |
| **Environment/System Adjustment** | {changes to make correct behavior easier} |
| **Failure Pre-mortem** | Risk 1: {risk} → Fallback: {fallback} |
| | Risk 2: {risk} → Fallback: {fallback} |

(Repeat for each KR)

---

## V (Appendix). Daily Routine Schedule

> Based on action system design, extract routines that can be fixed for calendar management and automation

### Daily Routines

| Time Slot | Routine Name | Related KR | Duration | Notes |
|-----------|--------------|------------|----------|-------|
| 06:00-06:30 | {routine} | {kr_ref} | 30min | {note} |
| 07:00-07:30 | {routine} | {kr_ref} | 30min | {note} |
| ... | | | | |

### Weekly Routines

| Day | Time Slot | Routine Name | Related KR | Duration | Notes |
|-----|-----------|--------------|------------|----------|-------|
| Monday | 19:00-20:00 | {routine} | {kr_ref} | 1h | {note} |
| Wednesday | 20:00-21:00 | {routine} | {kr_ref} | 1h | {note} |
| ... | | | | | |

### Monthly Routines

| Date | Time Slot | Routine Name | Related KR | Duration | Notes |
|------|-----------|--------------|------------|----------|-------|
| 1st of month | 09:00-10:00 | {routine} | {kr_ref} | 1h | {note} |
| 15th of month | 14:00-15:00 | {routine} | {kr_ref} | 1h | {note} |
| ... | | | | | |

### Routine Design Principles

- **Specific Timing**: Define clear start and end times for calendar integration
- **KR Alignment**: Each routine should align with a specific Key Result
- **Reasonable Duration**: Consider actual feasibility, avoid over-scheduling
- **Flexibility**: Mark which routines are adjustable vs. fixed

---

## VI. Recovery & Input Budget

### Recovery Activity Pool
| Activity | Energy Effect | Reservation Method |
|----------|---------------|-------------------|
| {activity} | {effect} | {reservation_method} |

### Input Activity Pool
| Direction | Expected Insights | Reservation Method |
|-----------|-------------------|-------------------|
| {direction} | {expected_insight} | {reservation_method} |

### Anti-Squeeze Strategy
- Most likely to be squeezed out: {item}
- Anti-squeeze measures: {measure}

> No frequency KPIs required - only "clear value + conscious reservation"

---

## VII. 12-Week Rhythm Planning

| Period | Theme | Aligned KR | Milestone (Verifiable) | Key Risks & Fallbacks |
|--------|-------|------------|------------------------|----------------------|
| Q1 (W1-12) | {theme} | {kr} | {milestone} | {risk_fallback} |
| Q2 (W13-24) | {theme} | {kr} | {milestone} | {risk_fallback} |
| Q3 (W25-36) | {theme} | {kr} | {milestone} | {risk_fallback} |
| Q4 (W37-48+) | {theme} | {kr} | {milestone} | {risk_fallback} |

---

## Appendix: Annual Calendar View

| Month | Quarter | Focus KR | Key Dates |
|-------|---------|----------|-----------|
| January | Q1 | | |
| February | Q1 | | |
| ... | | | |
| December | Q4 | | |

---

*This document is an annual strategic reference. Review and adjust during quarterly reviews.*
```

## Generation Guidelines

1. **Always ask user for input** at each phase, don't assume
2. **Use specific, measurable language** - avoid vague words like "improve", "enhance"
3. **Include verification evidence** for every KR
4. **Keep trade-offs explicit** - what NOT to do is as important as what to do
5. **Validate against Life Wheel** - ensure main battlefields address real imbalances
