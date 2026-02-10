# CLAUDE.md

## Project Overview

Zest Spec: A lightweight, file-driven development workflow for swappable coding agents.

## Spec-Driven Development (LeanSpec)

Specs are stored in `specs/`. Managed via `lean-spec` CLI.

### Commands

| Command                                      | Purpose               |
| -------------------------------------------- | --------------------- |
| `lean-spec board`                            | View project status   |
| `lean-spec search "query"`                   | Search existing specs |
| `lean-spec create <name>`                    | Create new spec       |
| `lean-spec update <spec> --status <status>`  | Update status         |
| `lean-spec link <spec> --depends-on <other>` | Link dependencies     |
| `lean-spec view <spec>`                      | View spec content     |

### Workflow

1. **Before**: `board` → `search` → confirm no duplicates
2. **During**: Update status to `in-progress`, link dependencies
3. **After**: Update status to `complete`

### Rules

- **Never** manually create spec files or edit frontmatter
- **Always** run `board` and `search` first to understand current state
- **Write spec for**: Multi-step features, breaking changes, design decisions
- **Skip spec for**: Bug fixes, trivial changes, self-explanatory refactors

### Spec 内容规范

- **简洁优先**: 只写大致流程和设计思路，不写详细实现代码
- **便于 Review**: 控制文档长度，让人能快速理解方案
- **伪代码/流程图**: 复杂逻辑用伪代码或步骤列表，而非完整代码
