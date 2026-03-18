---
name: everything-claude-code-conventions
description: Development conventions and patterns for everything-claude-code. JavaScript project with conventional commits.
---

# Everything Claude Code Conventions

> Generated from [affaan-m/everything-claude-code](https://github.com/affaan-m/everything-claude-code) on 2026-03-18

## Overview

This skill teaches Claude the development patterns and conventions used in everything-claude-code.

## Tech Stack

- **Primary Language**: JavaScript
- **Architecture**: hybrid module organization
- **Test Location**: separate

## When to Use This Skill

Activate this skill when:
- Making changes to this repository
- Adding new features following established patterns
- Writing tests that match project conventions
- Creating commits with proper message format

## Commit Conventions

Follow these commit message conventions based on 500 analyzed commits.

### Commit Style: Conventional Commits

### Prefixes Used

- `fix`
- `feat`
- `test`
- `docs`

### Message Guidelines

- Average message length: ~67 characters
- Keep first line concise and descriptive
- Use imperative mood ("Add feature" not "Added feature")


*Commit message example*

```text
feat: add everything-claude-code ECC bundle (.claude/commands/add-new-agent.md)
```

*Commit message example*

```text
fix: resolve 8 test failures on main (install pipeline, orchestrator, repair) (#564)
```

*Commit message example*

```text
merge: PR #529 — feat(skills): add documentation-lookup, bun-runtime, nextjs-turbopack; feat(agents): add rust-reviewer
```

*Commit message example*

```text
docs(skills): align documentation-lookup with CONTRIBUTING template; add cross-harness (Codex/Cursor) skill copies
```

*Commit message example*

```text
chore(config): governance and config foundation (#292)
```

*Commit message example*

```text
feat: add everything-claude-code ECC bundle (.claude/commands/add-new-skill.md)
```

*Commit message example*

```text
feat: add everything-claude-code ECC bundle (.claude/commands/feature-development.md)
```

*Commit message example*

```text
feat: add everything-claude-code ECC bundle (.claude/enterprise/controls.md)
```

## Architecture

### Project Structure: Single Package

This project uses **hybrid** module organization.

### Configuration Files

- `.github/workflows/ci.yml`
- `.github/workflows/maintenance.yml`
- `.github/workflows/monthly-metrics.yml`
- `.github/workflows/release.yml`
- `.github/workflows/reusable-release.yml`
- `.github/workflows/reusable-test.yml`
- `.github/workflows/reusable-validate.yml`
- `.opencode/package.json`
- `.opencode/tsconfig.json`
- `.prettierrc`
- `eslint.config.js`
- `package.json`

### Guidelines

- This project uses a hybrid organization
- Follow existing patterns when adding new code

## Code Style

### Language: JavaScript

### Naming Conventions

| Element | Convention |
|---------|------------|
| Files | camelCase |
| Functions | camelCase |
| Classes | PascalCase |
| Constants | SCREAMING_SNAKE_CASE |

### Import Style: Mixed Style

### Export Style: Named Exports


*Preferred export style*

```typescript
// Use named exports
export function calculateTotal() { ... }
export const TAX_RATE = 0.1
export interface Order { ... }
```

## Testing

### Test Framework

No specific test framework detected — use the repository's existing test patterns.

### File Pattern: `*.test.js`

### Test Types

- **Unit tests**: Test individual functions and components in isolation
- **Integration tests**: Test interactions between multiple components/services

### Coverage

This project has coverage reporting configured. Aim for 80%+ coverage.


## Error Handling

### Error Handling Style: Try-Catch Blocks


*Standard error handling pattern*

```typescript
try {
  const result = await riskyOperation()
  return result
} catch (error) {
  console.error('Operation failed:', error)
  throw new Error('User-friendly message')
}
```

## Common Workflows

These workflows were detected from analyzing commit patterns.

### Feature Development

Standard feature implementation workflow

**Frequency**: ~26 times per month

**Steps**:
1. Add feature implementation
2. Add tests for feature
3. Update documentation

**Files typically involved**:
- `manifests/*`
- `**/*.test.*`

**Example commit sequence**:
```
feat(skills): add documentation-lookup, bun-runtime, nextjs-turbopack; feat(agents): add rust-reviewer
docs(skills): align documentation-lookup with CONTRIBUTING template; add cross-harness (Codex/Cursor) skill copies
fix: address PR review — skill template (When to use, How it works, Examples), bun.lock, next build note, rust-reviewer CI note, doc-lookup privacy/uncertainty
```

### Add New Skill

Adds a new skill to the codebase, including documentation, agent configuration, and cross-harness copies.

**Frequency**: ~3 times per month

**Steps**:
1. Create or update SKILL.md in skills/<skill-name>/SKILL.md
2. Create or update agents/openai.yaml in .agents/skills/<skill-name>/agents/openai.yaml
3. Copy or update SKILL.md in .agents/skills/<skill-name>/SKILL.md and/or .cursor/skills/<skill-name>/SKILL.md
4. Register or update skill in manifests/install-components.json, install-modules.json, or install-profiles.json as needed
5. Update documentation (README.md, AGENTS.md) if required

**Files typically involved**:
- `skills/*/SKILL.md`
- `.agents/skills/*/SKILL.md`
- `.agents/skills/*/agents/openai.yaml`
- `.cursor/skills/*/SKILL.md`
- `manifests/install-components.json`
- `manifests/install-modules.json`
- `manifests/install-profiles.json`
- `README.md`
- `AGENTS.md`

**Example commit sequence**:
```
Create or update SKILL.md in skills/<skill-name>/SKILL.md
Create or update agents/openai.yaml in .agents/skills/<skill-name>/agents/openai.yaml
Copy or update SKILL.md in .agents/skills/<skill-name>/SKILL.md and/or .cursor/skills/<skill-name>/SKILL.md
Register or update skill in manifests/install-components.json, install-modules.json, or install-profiles.json as needed
Update documentation (README.md, AGENTS.md) if required
```

### Add New Agent

Adds a new agent to the codebase, including documentation and registration.

**Frequency**: ~2 times per month

**Steps**:
1. Create agent documentation in agents/<agent-name>.md
2. Register agent in AGENTS.md
3. Update rules/common/agents.md if needed
4. Add agent configuration in .codex/agents/<agent-name>.toml or .agents/skills/<skill-name>/agents/openai.yaml

**Files typically involved**:
- `agents/*.md`
- `AGENTS.md`
- `rules/common/agents.md`
- `.codex/agents/*.toml`
- `.agents/skills/*/agents/openai.yaml`

**Example commit sequence**:
```
Create agent documentation in agents/<agent-name>.md
Register agent in AGENTS.md
Update rules/common/agents.md if needed
Add agent configuration in .codex/agents/<agent-name>.toml or .agents/skills/<skill-name>/agents/openai.yaml
```

### Add Language Support

Adds support for a new programming language, including agents, commands, rules, and tests.

**Frequency**: ~1 times per month

**Steps**:
1. Add new agent(s) for the language in agents/<language>-*.md
2. Add new commands in commands/<language>-*.md
3. Add new rules in rules/<language>/*
4. Add or update test files in tests/hooks/ or tests/lib/
5. Update documentation (README.md, AGENTS.md) if required

**Files typically involved**:
- `agents/*-*.md`
- `commands/*-*.md`
- `rules/*/*`
- `tests/hooks/*.test.js`
- `tests/lib/*.test.js`
- `README.md`
- `AGENTS.md`

**Example commit sequence**:
```
Add new agent(s) for the language in agents/<language>-*.md
Add new commands in commands/<language>-*.md
Add new rules in rules/<language>/*
Add or update test files in tests/hooks/ or tests/lib/
Update documentation (README.md, AGENTS.md) if required
```

### Sync Skill Or Agent Documentation

Keeps documentation and catalog files in sync with the actual set of skills and agents.

**Frequency**: ~2 times per month

**Steps**:
1. Update AGENTS.md and README.md with current counts and lists
2. Update or validate manifests/install-*.json files
3. Update or validate scripts/ci/catalog.js and related CI/test files

**Files typically involved**:
- `AGENTS.md`
- `README.md`
- `manifests/install-components.json`
- `manifests/install-modules.json`
- `manifests/install-profiles.json`
- `scripts/ci/catalog.js`
- `tests/ci/validators.test.js`

**Example commit sequence**:
```
Update AGENTS.md and README.md with current counts and lists
Update or validate manifests/install-*.json files
Update or validate scripts/ci/catalog.js and related CI/test files
```

### Add Or Update Ecc Bundle Command

Adds or updates ECC bundle command documentation or configuration files.

**Frequency**: ~2 times per month

**Steps**:
1. Add or update markdown documentation in .claude/commands/*.md
2. Add or update configuration in .claude/skills/*/SKILL.md, .claude/identity.json, .claude/ecc-tools.json, .claude/team/*.json, etc.
3. Add or update agent/skill configuration in .codex/agents/*.toml or .agents/skills/*/agents/openai.yaml

**Files typically involved**:
- `.claude/commands/*.md`
- `.claude/skills/*/SKILL.md`
- `.claude/identity.json`
- `.claude/ecc-tools.json`
- `.claude/team/*.json`
- `.codex/agents/*.toml`
- `.agents/skills/*/agents/openai.yaml`

**Example commit sequence**:
```
Add or update markdown documentation in .claude/commands/*.md
Add or update configuration in .claude/skills/*/SKILL.md, .claude/identity.json, .claude/ecc-tools.json, .claude/team/*.json, etc.
Add or update agent/skill configuration in .codex/agents/*.toml or .agents/skills/*/agents/openai.yaml
```


## Best Practices

Based on analysis of the codebase, follow these practices:

### Do

- Use conventional commit format (feat:, fix:, etc.)
- Follow *.test.js naming pattern
- Use camelCase for file names
- Prefer named exports

### Don't

- Don't write vague commit messages
- Don't skip tests for new features
- Don't deviate from established patterns without discussion

---

*This skill was auto-generated by [ECC Tools](https://ecc.tools). Review and customize as needed for your team.*
