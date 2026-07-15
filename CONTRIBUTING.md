# Contributing to `skills-gamedev`

Maintainer: **Poorvith M P** · v0.1 · last updated July 2026

## Skill format (skill-creator)

Every skill lives at:

```text
skills/<skill-id>/
├── SKILL.md
├── references/NOTE.md
└── assets/NOTE.md
```

Rules:
1. Folder name must equal frontmatter `name` (kebab-case).
2. `description` must include **what** the skill does and **when** to use it (trigger phrases).
3. Body uses imperative instructions; explain **why** for critical rules.
4. Keep `SKILL.md` lean; put large docs in `references/` only when needed.
5. `assets/` is for templates and media used in outputs — not instructions.
6. **No credits, personal handles, machine paths, or third-party source URLs** in skill bodies.
7. License is MIT under Poorvith M P.

## Pull request checklist

- [ ] New/changed skill has `SKILL.md` + empty `references/` + `assets/` notes
- [ ] Description is trigger-rich and under ~1024 characters
- [ ] No duplicate skill-id in this repo
- [ ] CHANGELOG.md updated under Unreleased or a version heading
- [ ] No personal data or secrets

## Local install (Claude Code)

Copy a skill folder into `~/.claude/skills/<skill-id>/` or `.claude/skills/<skill-id>/`.
