# Life Planner Plugin

[English](README.md) | [中文](README_CN.md)

A personal strategic planning and execution system based on the Life Wheel methodology - Claude Code Plugin.

## Features

- **Annual Planning**: Complete annual strategic planning workflow (Phase 0-8)
- **Monthly Planning**: Monthly execution plans aligned with annual goals
- **Monthly Review**: Structured monthly retrospectives with rolling adjustments
- **Life Wheel Assessment**: 8-dimension life balance evaluation

## Installation

```bash
/plugin install github:charliecai/life-planner
```

## Usage

Once installed, the plugin automatically triggers when you mention these keywords:

| Scenario | Trigger Keywords |
|----------|-----------------|
| Annual Planning | "annual plan", "annual planning", "年度计划", "年度规划" |
| Annual Review | "annual review", "year review", "年度复盘", "年度回顾" |
| Monthly Planning | "monthly plan", "monthly planning", "月度计划", "月度规划" |
| Monthly Review | "monthly review", "月度复盘", "月度回顾" |
| Life Wheel | "life wheel", "life balance", "生命之轮", "人生规划" |

### Example Conversations

```
I want to start my 2025 annual planning
```

```
Help me do my December monthly review
```

```
Create a monthly plan for January
```

## Methodology Overview

### Life Wheel - 8 Dimensions

1. **Health** (body, energy, sleep)
2. **Career / Studies**
3. **Wealth / Financial Security**
4. **Family**
5. **Intimate Relationships**
6. **Social / Friends**
7. **Personal Growth** (cognition, skills)
8. **Leisure / Fun / Mental Recovery**

### Core Principles

- **Diagnose structure before discussing goals**
- **Maximum 2-3 battlefields per year**
- **Subtraction before addition**
- **Recovery and input must be protected**
- **All goals must be verifiable**

### Workflow

```
Phase 0: Reality Check & Role Confirmation
    ↓
Phase 1-2: Life Wheel Scan + Annual Review
    ↓
Phase 3-4: Strategic Focus + OKR Setting
    ↓
Phase 5-6: Action System + Recovery Budget
    ↓
Phase 7-8: Annual Battle Map + 12-Week Rhythm
    ↓
Phase 9: Monthly Planning ←──┐
    ↓                        │
Phase 10: Monthly Review ────┘
```

## Generated Documents

The plugin helps you generate the following Markdown documents:

| Document Type | Filename Format |
|--------------|-----------------|
| Annual Plan | `annual-plan-{year}.md` |
| Monthly Plan | `monthly-plan-{year}-{month}.md` |
| Monthly Review | `monthly-review-{year}-{month}.md` |

## Project Structure

```
life-planner/
├── .claude-plugin/
│   ├── plugin.json          # Plugin manifest
│   └── marketplace.json     # Marketplace config
├── skills/
│   └── life-planner/
│       ├── SKILL.md                    # Main skill file
│       ├── ANNUAL-PLAN-TEMPLATE.md     # Annual plan template
│       ├── MONTHLY-PLAN-TEMPLATE.md    # Monthly plan template
│       └── MONTHLY-REVIEW-TEMPLATE.md  # Monthly review template
└── README.md
```

## Development

### Local Testing

```bash
# Clone the repo
git clone https://github.com/charliecai/life-planner.git

# Load as plugin
claude --plugin-dir ./life-planner
```

### Validate Plugin

```bash
/plugin validate ./life-planner
```

## License

MIT License

## Credits

This system is based on the "Holographic Life Strategist v2.2" methodology.

