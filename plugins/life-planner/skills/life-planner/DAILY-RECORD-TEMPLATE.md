# Daily Record Template

Use this template when creating or updating daily record files.

**IMPORTANT: For file operations, use Bash heredoc method (see SKILL.md Method 1)**
- All sections should be generated in ONE Bash call using { } braces
- This ensures only ONE user confirmation is needed

## File Naming Convention

```
{year}/{year}{month}/daily-records-{year}-{month}.md
```

Example: `2026/202601/daily-records-2026-01.md`

## Document Structure

```markdown
# {Year}/{Month} Daily Records

> Created: {first_record_date}
> Last Updated: {last_update_date}
> Total Records This Month: {total_count}

---

## Record Summary

| Category | Count | Description |
|----------|-------|-------------|
| Exercise & Fitness | {count} | Running, gym, swimming, etc. |
| Social Meetings | {count} | Gatherings, dates, meetings, etc. |
| Expenses | {count} | Shopping, purchases, etc. |
| Free Records | {count} | Other records |

---

## Detailed Records

### Exercise & Fitness

| Date | Content | Notes |
|------|---------|-------|
| {date} | {content} | {note} |

### Social Meetings

| Date | Content | Notes |
|------|---------|-------|
| {date} | {content} | {note} |

### Expenses

| Date | Content | Amount | Notes |
|------|---------|--------|-------|
| {date} | {content} | {amount} | {note} |

### Free Records

| Date | Content | Notes |
|------|---------|-------|
| {date} | {content} | {note} |

---

*This file is automatically maintained by the daily record feature*
```

## Category Keywords

Use these keywords to automatically classify records:

| Category | Keywords |
|----------|----------|
| Exercise & Fitness | run, running, gym, swim, swimming, workout, exercise, yoga, cycling, basketball, football, soccer, badminton, tennis, table tennis, hiking, climbing, walking, weightlifting, squat, push-up, sit-up, pilates, stretching, cardio, aerobic, 跑步, 健身, 游泳, 锻炼, 运动, 瑜伽, 骑行, 篮球, 足球, 羽毛球, 网球, 乒乓, 徒步, 爬山, 健走, 举重, 深蹲, 俯卧撑, 仰卧起坐, 普拉提, 拉伸, 有氧, 无氧 |
| Social Meetings | meeting, date, party, gathering, dinner, hangout, reunion, visit, meetup, social, 见面, 约会, 聚会, 聚餐, 饭局, 派对, 聚一聚, 叙旧, 相亲, 会面, 拜访, 串门, 团建, 联谊 |
| Expenses | bought, spent, paid, purchase, cost, payment, order, shopping, expense, 买了, 花了, 消费, 购买, 支出, 付款, 下单, 充值, 订购, 购物, 采购, 开销, 报销 |
| Free Records | (default, when no other keywords match) |

## Amount Extraction Patterns

For expense records, extract amounts using these patterns:
- `spent 100` / `$100` / `100 dollars` → $100
- `花了100元` / `花费100` → ¥100
- `100元` / `100块` → ¥100
- `￥100` / `¥100` → ¥100

## Generation Guidelines

1. **New file creation** - Use `cat >` to create the initial file
2. **Appending records** - Use `cat >>` or direct table row insertion
3. **Update summary counts** - After adding records, update the summary table
4. **Maintain chronological order** - Sort records by date within each category
5. **Date format** - Use YYYY-MM-DD format for all dates
