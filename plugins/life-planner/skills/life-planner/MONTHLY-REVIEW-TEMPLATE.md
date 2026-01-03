# Monthly Review Template

Use this template when generating monthly review documents.

**IMPORTANT: For document generation, use Bash heredoc method (see SKILL.md Method 1)**
- This template is ~238 lines, which is too long for Write tool
- **Generate ALL sections in ONE Bash call using { } braces**
- **This ensures only ONE user confirmation is needed**
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

## Document Structure

```markdown
# {Year}/{Month} Monthly Review

> Review Date: {date}
> Monthly Theme: {monthly_theme}
> Annual Theme: {annual_theme}

---

## Daily Records Summary (if available)

> Data from `daily-records-{year}-{month}.md`. Skip this section if no daily records file exists.

| Category | Count This Month | Notes |
|----------|------------------|-------|
| Exercise & Fitness | {count} | {note} |
| Social Meetings | {count} | {note} |
| Expenses | {count} entries / {total} | {note} |
| Free Records | {count} | {note} |

---

## I. Result Review

### Must Win Verification

| Item | Status | Details |
|------|--------|---------|
| **Must Win** | {must_win_description} | |
| **Achievement Status** | ✅ Achieved / ❌ Not Achieved / ⚠️ Partially Achieved | |
| **Verification Evidence** | {actual_evidence} | |
| **Gap Analysis** | {gap_analysis_if_not_achieved} | |

### Result Commitment Verification

| Commitment | Status | Verification Evidence | Notes |
|------------|--------|----------------------|-------|
| {commitment_1} | ✅/❌/⚠️ | {evidence} | {notes} |
| {commitment_2} | ✅/❌/⚠️ | {evidence} | {notes} |
| {commitment_3} | ✅/❌/⚠️ | {evidence} | {notes} |

**Achievement Rate**: {x}/{total} = {percentage}%

### Top 3 Most Effective Investments
1. {effective_1} - Output: {output}
2. {effective_2} - Output: {output}
3. {effective_3} - Output: {output}

### Top 3 "Busy but Ineffective" Activities
1. {ineffective_1} - Cost: {cost}
2. {ineffective_2} - Cost: {cost}
3. {ineffective_3} - Cost: {cost}

---

## II. Cost & System Health

### Cost Events This Month
| Cost Type | Specific Event | Impact Level |
|-----------|---------------|--------------|
| Health Cost | {event} | High/Medium/Low |
| Relationship Cost | {event} | High/Medium/Low |
| Long-term Capability Cost | {event} | High/Medium/Low |

### Mental Occupation Analysis
- **Highest Mental Occupation Source**: {source}
- **Reason for Occupation**: {reason}
- **Controllable**: Yes/No
- **Handling Strategy**: {strategy}

### Energy & Recovery Status
| Indicator | Score (1-10) | Notes |
|-----------|--------------|-------|
| Overall Energy Level | {score} | {notes} |
| Sleep Quality | {score} | {notes} |
| Recovery Adequacy | {score} | {notes} |

### System Sustainability Warning

> **If this continues for 3 months, what happens to the system?**

{sustainability_analysis}

- [ ] Sustainable, maintain current rhythm
- [ ] Needs fine-tuning, {adjustment_needed}
- [ ] Danger signal, must change immediately {what_to_change}

---

## III. Life Wheel Quick Retest

### This Month vs Last Month

| Dimension | Last Month | This Month | Change | Reason |
|-----------|------------|------------|--------|--------|
| Health | {prev} | {curr} | {+/-n} | {reason_if_changed} |
| Career/Studies | {prev} | {curr} | {+/-n} | |
| Wealth/Financial Security | {prev} | {curr} | {+/-n} | |
| Family | {prev} | {curr} | {+/-n} | |
| Intimate Relationships | {prev} | {curr} | {+/-n} | |
| Social/Friends | {prev} | {curr} | {+/-n} | |
| Personal Growth | {prev} | {curr} | {+/-n} | |
| Leisure/Recovery | {prev} | {curr} | {+/-n} | |

### Analysis of Most Changed Dimensions (2-3 items)

**{dimension_1}**: {prev} → {curr} ({change})
- Change Reason: {reason}
- As Expected: Yes/No
- Next Month Focus: {focus}

**{dimension_2}**: {prev} → {curr} ({change})
- Change Reason: {reason}
- As Expected: Yes/No
- Next Month Focus: {focus}

---

## IV. Failure Pattern Recognition

### Repeated Failure Patterns This Month (occurred ≥2 times)

| Pattern | Occurrences | Specific Scenarios |
|---------|-------------|-------------------|
| {pattern_1} | {count} | {scenarios} |
| {pattern_2} | {count} | {scenarios} |

### Root Cause Analysis (not symptoms, but root causes)

**Pattern: {pattern_1}**
- Surface Reason: {surface_reason}
- Root Cause: {root_cause}
- System/Environment Factor: {systemic_factor}

**Pattern: {pattern_2}**
- Surface Reason: {surface_reason}
- Root Cause: {root_cause}
- System/Environment Factor: {systemic_factor}

### Correction Strategies (system/environment/constraints to change next month)

| Failure Pattern | Correction Strategy | Implementation |
|-----------------|---------------------|----------------|
| {pattern_1} | {strategy} | {implementation} |
| {pattern_2} | {strategy} | {implementation} |

---

## V. Subtraction Commitment Execution

| Planned to Stop/Reduce | Execution Status | Effect Released |
|------------------------|------------------|-----------------|
| {item_1} | ✅ Executed / ❌ Not Executed / ⚠️ Partial | {effect} |
| {item_2} | ✅/❌/⚠️ | {effect} |
| {item_3} | ✅/❌/⚠️ | {effect} |

**Subtraction Execution Reflection**: {reflection}

---

## VI. Recovery & Input Execution

### Recovery Activity Execution
| Planned Activity | Actual Execution | Energy Effect |
|------------------|------------------|---------------|
| {activity_1} | {actual_execution} | High/Medium/Low/Not Executed |
| {activity_2} | {actual_execution} | High/Medium/Low/Not Executed |

### Input Activity Execution
| Planned Direction | Actual Execution | Insights Gained |
|-------------------|------------------|-----------------|
| {direction_1} | {actual_execution} | {insight_gained} |
| {direction_2} | {actual_execution} | {insight_gained} |

### Squeeze Situation
- **Squeezed Activity**: {squeezed_activity}
- **Disruptor**: {disruptor}
- **Next Month Anti-Squeeze Adjustment**: {adjustment}

---

## VII. Next Month Rolling Adjustment

### Next Month Theme
- **Theme**: {next_month_theme}
- **Alignment Notes**: {alignment_explanation}

### Commitment Adjustment

| This Month Commitment | Adjustment Decision | Reason |
|-----------------------|---------------------|--------|
| {commitment_1} | Continue/Stop/Replace with {new} | {reason} |
| {commitment_2} | Continue/Stop/Replace with {new} | {reason} |
| {commitment_3} | Continue/Stop/Replace with {new} | {reason} |

### Next Month Must Win
- **Must Win**: {next_must_win}
- **Verification Evidence**: {evidence}
- **Aligned KR**: {kr_reference}

### Next Month Subtraction Commitments
1. {subtraction_1}
2. {subtraction_2}
3. {subtraction_3}

### Next Month Recovery & Input Reservation
- **Recovery Reservation**: {recovery_reservation}
- **Input Reservation**: {input_reservation}
- **Anti-Squeeze Strategy**: {protection_strategy}

---

## VIII. Key Insights This Month

> Summarize the most important learnings in 1-3 sentences

{key_insights}

---

## Appendix: Annual KR Progress Update

| KR | Annual Target | Current Progress | This Month's Progress | Expected Achievement |
|----|---------------|------------------|----------------------|---------------------|
| {kr_1} | {target} | {current}% | {this_month_progress} | 🟢/🟡/🔴 |
| {kr_2} | {target} | {current}% | {this_month_progress} | 🟢/🟡/🔴 |
| {kr_3} | {target} | {current}% | {this_month_progress} | 🟢/🟡/🔴 |

Legend: 🟢 On Track | 🟡 Slight Deviation | 🔴 Significantly Behind

---

*Next month plan generation date: {next_plan_date}*
```

## Generation Guidelines

1. **Evidence-based review** - every claim needs supporting evidence
2. **Pattern recognition** - focus on repeated failures (≥2 times), not one-offs
3. **Root cause analysis** - dig deeper than surface symptoms
4. **System thinking** - ask "what if this continues for 3 months?"
5. **Rolling adjustment** - every review naturally leads to next month's plan
6. **Life Wheel tracking** - maintain continuity of dimension scores
7. **KR progress update** - always connect back to annual goals
