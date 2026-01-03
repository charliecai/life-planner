# Monthly Plan Template

Use this template when generating monthly planning documents.

**IMPORTANT: For document generation, use Bash heredoc method (see SKILL.md Method 1)**
- This template is ~180 lines, which is too long for Write tool
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
# {Year}/{Month} Monthly Execution Plan

> Generated: {date}
> Annual Theme Alignment: {annual_theme}
> Quarterly Theme Alignment: {quarterly_theme}

---

## Monthly Theme

- **This Month's Theme**: {monthly_theme}
- **Alignment Notes**: {how_this_aligns_with_annual_and_quarterly_themes}

---

## Monthly Success Criteria

How to determine success at month's end? (2-3 items, at least 2 achieved = success)

1. {criterion_1}
   - Verification: {evidence}
2. {criterion_2}
   - Verification: {evidence}
3. {criterion_3} (optional)
   - Verification: {evidence}

---

## Must Win Item

> If only one thing can be accomplished this month, it must be this.

- **Must Win Description (Result State)**: {result_state_description}
- **Verification Evidence**: {specific_evidence}
- **Aligned Annual KR**: {kr_reference}

---

## Result Commitments

Maximum 3 items, each must align with annual KR, must be "result state" not "effort process".

### Commitment 1
| Item | Content |
|------|---------|
| **Commitment** | {result_commitment} |
| **Aligned KR** | {kr_reference} |
| **Verification** | {evidence} |
| **Deadline** | {deadline} |

### Commitment 2
| Item | Content |
|------|---------|
| **Commitment** | {result_commitment} |
| **Aligned KR** | {kr_reference} |
| **Verification** | {evidence} |
| **Deadline** | {deadline} |

### Commitment 3 (Optional)
| Item | Content |
|------|---------|
| **Commitment** | {result_commitment} |
| **Aligned KR** | {kr_reference} |
| **Verification** | {evidence} |
| **Deadline** | {deadline} |

---

## Key Action System

Design execution support system for each commitment.

### Commitment 1 Action System

| Element | Content |
|---------|---------|
| **Minimum Action** (5-20 min to start) | {minimal_action} |
| **Environment/System Adjustment** | {environment_change} |
| **Failure Pre-mortem - Risk 1** | {risk_1} |
| **Fallback 1** | {fallback_1} |
| **Failure Pre-mortem - Risk 2** | {risk_2} |
| **Fallback 2** | {fallback_2} |

### Commitment 2 Action System

| Element | Content |
|---------|---------|
| **Minimum Action** | {minimal_action} |
| **Environment/System Adjustment** | {environment_change} |
| **Failure Pre-mortem - Risk 1** | {risk_1} |
| **Fallback 1** | {fallback_1} |
| **Failure Pre-mortem - Risk 2** | {risk_2} |
| **Fallback 2** | {fallback_2} |

---

## Subtraction Commitments

1-3 things to stop/reduce this month (freeing up time, energy, mental bandwidth)

1. **Stop/Reduce**: {item_1}
   - Reason: {reason}
   - Freed Resources: {freed_resource}

2. **Stop/Reduce**: {item_2}
   - Reason: {reason}
   - Freed Resources: {freed_resource}

3. **Stop/Reduce**: {item_3} (optional)
   - Reason: {reason}
   - Freed Resources: {freed_resource}

---

## Recovery & Input Reservation

> No KPIs required - only "clear value + conscious reservation"

### Recovery Reservation
| Activity | Reservation Method | Suggested Frequency |
|----------|-------------------|---------------------|
| {recovery_activity} | {how_to_reserve} | {frequency} |

### Input Reservation
| Direction | Reservation Method | Expected Gain |
|-----------|-------------------|---------------|
| {input_direction} | {how_to_reserve} | {expected_gain} |

### Anti-Squeeze Strategy
- **Most Likely Disruptor**: {potential_disruptor}
- **Protection Strategy**: {protection_strategy}

---

## Weekly Rhythm Suggestions

### Fixed Weekly Windows
| Window Type | Time Slot | Purpose |
|-------------|-----------|---------|
| Deep Work Block | {time_slot} | {purpose} |
| Review Time | {time_slot} | Weekly review |
| Recovery Time | {time_slot} | {recovery_activity} |

### Key Dates This Month
| Date | Item | Type |
|------|------|------|
| {date} | {item} | Deadline/Delivery/Checkpoint |

---

## Annual Plan Alignment Check

| Check Item | Status |
|------------|--------|
| Does Must Win advance annual KR? | ✅/❌ |
| Are commitments focused on main battlefield dimensions? | ✅/❌ |
| Does subtraction align with annual subtraction list? | ✅/❌ |
| Does recovery reservation protect key activities? | ✅/❌ |

---

*Next review date: {next_review_date}*
```

## Generation Guidelines

1. **Must Win is singular** - only ONE must-win item per month
2. **Maximum 3 commitments** - prevent task list syndrome
3. **Results, not efforts** - "Complete X" not "Try to do X"
4. **Subtraction is mandatory** - every plan must include what to stop
5. **Recovery is non-negotiable** - always include recovery reservations
6. **Verify alignment** - every commitment should trace back to annual KR
