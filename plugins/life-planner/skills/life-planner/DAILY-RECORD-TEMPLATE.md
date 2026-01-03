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

## Record Summary (Life Wheel 8 Dimensions)

| Dimension | Count | Description |
|-----------|-------|-------------|
| Health | {count} | Exercise, sleep, medical, diet |
| Career/Studies | {count} | Work, projects, learning |
| Wealth | {count} | Income, expenses, investments |
| Family | {count} | Family time and activities |
| Intimate Relationships | {count} | Partner activities |
| Social/Friends | {count} | Social gatherings, friendships |
| Personal Growth | {count} | Reading, skills, reflection |
| Leisure/Fun | {count} | Entertainment, relaxation |

---

## Detailed Records

### Health

| Date | Content | Notes |
|------|---------|-------|
| {date} | {content} | {note} |

### Career/Studies

| Date | Content | Notes |
|------|---------|-------|
| {date} | {content} | {note} |

### Wealth

| Date | Content | Amount | Notes |
|------|---------|--------|-------|
| {date} | {content} | {amount} | {note} |

### Family

| Date | Content | Notes |
|------|---------|-------|
| {date} | {content} | {note} |

### Intimate Relationships

| Date | Content | Notes |
|------|---------|-------|
| {date} | {content} | {note} |

### Social/Friends

| Date | Content | Notes |
|------|---------|-------|
| {date} | {content} | {note} |

### Personal Growth

| Date | Content | Notes |
|------|---------|-------|
| {date} | {content} | {note} |

### Leisure/Fun

| Date | Content | Notes |
|------|---------|-------|
| {date} | {content} | {note} |

---

*This file is automatically maintained by the daily record feature*
```

## Dimension Keywords (Life Wheel)

Use these keywords to automatically classify records based on Life Wheel dimensions:

| Dimension | Keywords |
|-----------|----------|
| Health | run, running, gym, swim, swimming, workout, exercise, yoga, cycling, walking, weightlifting, squat, push-up, pilates, stretching, cardio, sleep, doctor, hospital, medicine, diet, checkup, 跑步, 健身, 游泳, 锻炼, 运动, 瑜伽, 骑行, 健走, 举重, 深蹲, 俯卧撑, 普拉提, 拉伸, 有氧, 无氧, 睡眠, 看病, 医院, 吃药, 饮食, 体检, 早睡, 熬夜 |
| Career/Studies | work, project, meeting, presentation, deadline, study, course, exam, interview, promotion, office, client, report, 工作, 项目, 会议, 汇报, 截止, 学习, 课程, 考试, 面试, 晋升, 加班, 办公, 客户, 述职, 培训 |
| Wealth | bought, spent, paid, invest, salary, bonus, save, budget, income, expense, purchase, shopping, cost, payment, 买了, 花了, 消费, 投资, 工资, 奖金, 存钱, 预算, 收入, 支出, 理财, 购买, 购物, 开销, 报销 |
| Family | family, parents, mom, dad, mother, father, sibling, brother, sister, grandparents, home, 家人, 父母, 爸, 妈, 爸妈, 兄弟, 姐妹, 爷爷, 奶奶, 外公, 外婆, 回家, 家庭, 孩子, 儿子, 女儿 |
| Intimate Relationships | partner, spouse, wife, husband, boyfriend, girlfriend, date, anniversary, romance, 伴侣, 老婆, 老公, 男友, 女友, 约会, 纪念日, 恋爱, 结婚, 爱人, 对象 |
| Social/Friends | friend, party, gathering, hangout, reunion, meetup, social, dinner party, 朋友, 聚会, 聚餐, 饭局, 派对, 叙旧, 团建, 联谊, 见面, 拜访, 串门 |
| Personal Growth | book, read, learn, course, skill, practice, reflect, meditation, journal, 看书, 阅读, 学习, 技能, 练习, 反思, 思考, 成长, 冥想, 写日记, 复盘 |
| Leisure/Fun | movie, game, travel, vacation, hobby, relax, music, concert, entertainment, hiking, 电影, 游戏, 旅行, 度假, 爱好, 放松, 音乐, 演唱会, 休息, 娱乐, 徒步, 爬山, 露营 |

**Priority**: Health > Career/Studies > Wealth > Family > Intimate Relationships > Social/Friends > Personal Growth > Leisure/Fun

**Default behavior**: If no keyword matches, prompt user to select a dimension manually.

## Amount Extraction Patterns (Wealth dimension only)

For Wealth dimension records, extract amounts using these patterns:
- `spent 100` / `$100` / `100 dollars` → $100
- `花了100元` / `花费100` → ¥100
- `100元` / `100块` → ¥100
- `￥100` / `¥100` → ¥100

## Generation Guidelines

1. **New file creation** - Use `cat >` to create the initial file
2. **Appending records** - Use `cat >>` or direct table row insertion
3. **Update summary counts** - After adding records, update the summary table
4. **Maintain chronological order** - Sort records by date within each dimension
5. **Date format** - Use YYYY-MM-DD format for all dates
6. **Dimension alignment** - Each record maps to exactly one Life Wheel dimension
