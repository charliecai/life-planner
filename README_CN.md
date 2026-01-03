# Life Planner Plugin

[English](README.md) | [中文](README_CN.md)

基于「生命之轮」方法论的个人年度战略规划与执行系统 - Claude Code 插件。

## 功能特性

- **年度规划**：完整的年度战略规划流程（Phase 0-8）
- **月度计划**：对齐年度目标的月度执行计划
- **月度回顾**：结构化的月度复盘与滚动调整
- **生命之轮评估**：8 维度人生平衡扫描

## 安装

```bash
# 1. 添加市场
/plugin marketplace add charliecai/life-planner

# 2. 安装插件
/plugin install life-planner@life-planner-marketplace

# 如果需要卸载
/plugin uninstall life-planner@life-planner-marketplace
```

## 使用方法

安装后，当你在对话中提到以下关键词时，插件会自动触发：

| 触发场景 | 关键词示例 |
|---------|-----------|
| 年度规划 | "年度计划"、"年度规划"、"annual planning" |
| 年度复盘 | "年度复盘"、"年度回顾"、"annual review" |
| 月度计划 | "月度计划"、"月度规划"、"monthly planning" |
| 月度回顾 | "月度复盘"、"月度回顾"、"monthly review" |
| 生命之轮 | "生命之轮"、"人生规划"、"life wheel" |

### 示例对话

```
我想开始做2025年的年度规划
```

```
帮我做一下12月的月度回顾
```

```
制定1月份的月度计划
```

## 方法论概述

### 生命之轮 8 维度

1. **健康**（身体、精力、睡眠）
2. **事业 / 学业**
3. **财富 / 财务安全**
4. **家庭**
5. **亲密关系**
6. **社交 / 朋友圈**
7. **个人成长**（认知、技能）
8. **休闲 / 乐趣 / 心理恢复**

### 核心原则

- **先诊断结构，再谈目标**
- **年度最多 2-3 个主战场**
- **先做减法，再做加法**
- **恢复与输入必须被保护**
- **所有目标必须可验证**

### 工作流程

```mermaid
flowchart TD
    %% 定义样式
    classDef process fill:#e1f5fe,stroke:#01579b,stroke-width:2px;
    classDef decision fill:#fff9c4,stroke:#fbc02d,stroke-width:2px;
    classDef storage fill:#f3e5f5,stroke:#7b1fa2,stroke-width:2px;
    classDef terminator fill:#e0e0e0,stroke:#333,stroke-width:2px;
    classDef critical fill:#ffccbc,stroke:#d84315,stroke-width:2px,stroke-dasharray: 5 5;

    %% =======================
    %% Phase 1: 年度计划初始化
    %% =======================
    Start((开始: 新建年度计划)):::terminator
    CheckLastYear{检查: 上一年复盘?}:::decision
    CreateLastReview[动作: 补录上一年复盘]:::process
    GenAnnualPlan[系统: 生成年度计划]:::process

    Start --> CheckLastYear
    CheckLastYear -- 无 (且确认做) --> GenAnnualPlan
    CheckLastYear -- 无 (去补录) --> CreateLastReview --> GenAnnualPlan
    CheckLastYear -- 有 --> GenAnnualPlan

    %% =======================
    %% Phase 2: 后续动作分发 (并行/独立)
    %% =======================
    PlanReady((年度计划完成)):::terminator
    GenAnnualPlan --> PlanReady

    UserChoice{用户后续操作}:::decision
    PlanReady --> UserChoice

    %% 分支 A: 拆分月度计划 (核心路径)
    ActionSplit[动作: 拆分/创建<br>首月月度计划]:::critical

    %% 分支 B: 同步日历 (可选路径)
    ActionCalendar[动作: Routine同步日历]:::process
    CheckMonthExists_Cal{检查: 是否已有<br>月度计划?}:::decision
    PromptForMonth_Cal[提示: 建议创建月度计划]:::process

    %% 连线逻辑
    UserChoice -- 拆分月度 --> ActionSplit
    UserChoice -- 同步日历 --> ActionCalendar

    ActionCalendar --> CheckMonthExists_Cal
    CheckMonthExists_Cal -- 无 --> PromptForMonth_Cal
    PromptForMonth_Cal --> ActionSplit
    CheckMonthExists_Cal -- 有 (结束) --> DoneCal((日历同步完成)):::terminator

    %% =======================
    %% Phase 3: 日常记录 (带校验)
    %% =======================
    subgraph DailyLoop [日常记录闭环]
        direction TB
        UserRecord[用户: 触发日常记录]:::process
        CheckMonthExists_Rec{检查: 当月是否有<br>月度计划?}:::decision
        PromptForMonth_Rec[提示: 请先创建本月计划]:::process
        SaveLog[(系统: 存入记录文件)]:::storage
    end

    %% 记录时的校验逻辑
    UserRecord --> CheckMonthExists_Rec
    CheckMonthExists_Rec -- 有 --> SaveLog
    CheckMonthExists_Rec -- 无 --> PromptForMonth_Rec

    %% 关键连接：如果记录时发现没计划，跳转去创建
    PromptForMonth_Rec -.-> ActionSplit
    ActionSplit -.->|创建完成后| SaveLog

    %% =======================
    %% Phase 4 & 5: 复盘 (简略)
    %% =======================
    SaveLog -.-> MonthReview[月度复盘]
    MonthReview --> NextMonthPlan[创建下月计划]
    NextMonthPlan -.-> YearReview[年度复盘]
```

## 生成的文档

插件会帮你生成以下文档：

| 文档类型 | 文件名格式 | 位置 |
|---------|-----------|------|
| 年度计划 | `annual-plan-{year}.md` | `{year}/` |
| 年度复盘 | `annual-review-{year}.md` | `{year}/` |
| 日历文件 | `routines-{year}.ics` | `{year}/` |
| 月度计划 | `monthly-plan-{year}-{month}.md` | `{year}/{year}{month}/` |
| 月度复盘 | `monthly-review-{year}-{month}.md` | `{year}/{year}{month}/` |
| 每日记录 | `daily-records-{year}-{month}.md` | `{year}/{year}{month}/` |

## 项目结构

```
life-planner/
├── .claude-plugin/
│   └── marketplace.json              # 市场配置
├── plugins/
│   └── life-planner/
│       ├── .claude-plugin/
│       │   └── plugin.json           # 插件清单
│       └── skills/
│           └── life-planner/
│               ├── SKILL.md                    # 主技能文件
│               ├── ANNUAL-PLAN-TEMPLATE.md     # 年度计划模板
│               ├── MONTHLY-PLAN-TEMPLATE.md    # 月度计划模板
│               └── MONTHLY-REVIEW-TEMPLATE.md  # 月度回顾模板
└── README.md
```

## 开发

### 本地测试

```bash
# 克隆项目
git clone https://github.com/charliecai/life-planner.git

# 以插件模式加载
claude --plugin-dir ./life-planner
```

### 验证插件

```bash
/plugin validate ./life-planner
```

## 许可证

MIT License

## 参考资料

本系统基于「全息人生战略官 v2.2」方法论设计。

