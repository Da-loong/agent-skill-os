# Integrated Skills — Batch 1

A curated collection, not a claim of ownership. Each SKILL.md below is copied from its original public repository, with its source, path and file SHA recorded in SOURCES.md. This batch is a start, not a complete integration of skills.sh or of the 1000+ entries in ComposioHQ/awesome-claude-skills.

## Batch 1 — 5 skills

| Skill | Source | Why it is here |
|---|---|---|
| find-skills | vercel-labs/skills | skills.sh All Time #1, 4.1M installs shown on skills.sh. Discovers and installs other skills. |
| grill-me | mattpocock/skills | skills.sh All Time #2, 1.4M installs shown on skills.sh. A relentless interview to sharpen a plan or design. Note: its SKILL.md is a 157-byte stub that calls the "grilling" agent in the source repo; the full session logic lives in the source repo, not in this file alone. |
| tdd | mattpocock/skills | skills.sh All Time, 1.2M installs shown on skills.sh. Test-driven development, red-green loop. This is mattpocock's tdd, distinct from obra/superpowers' test-driven-development. |
| frontend-design | anthropics/skills | skills.sh All Time #14, 1.0M installs shown on skills.sh. Distinctive, intentional visual design, not templated defaults. |
| changelog-generator | ComposioHQ/awesome-claude-skills | In-repo skill from the Composio curated list. Turns git commits into user-facing changelogs. |

## Install from the originals (recommended)

Use the original install routes where possible, so you get updates:

```bash
npx skills add vercel-labs/skills --skill find-skills
npx skills add mattpocock/skills --skill grill-me
npx skills add mattpocock/skills --skill tdd
npx skills add anthropics/skills --skill frontend-design
```

For changelog-generator, see the ComposioHQ/awesome-claude-skills repository, folder `changelog-generator/`.

## What is in this folder

```
skills/
  find-skills/SKILL.md
  grill-me/SKILL.md
  tdd/SKILL.md
  frontend-design/SKILL.md
  changelog-generator/SKILL.md
SOURCES.md
README.md
```

## Licenses and attribution

- Each skill remains under its original author's license. Do not remove source attribution when reusing.
- anthropics/skills frontend-design frontmatter notes: "Complete terms in LICENSE.txt" in its source repo.
- ComposioHQ/awesome-claude-skills list itself is Apache-2.0; individual skills in that list have their own authors and licenses.
- If a source license forbids a use you have in mind, follow the source license, not this README.

## Next batches

Next candidates, not yet integrated: agent-browser (vercel-labs), improve-codebase-architecture (mattpocock), docx/pdf/pptx/xlsx (anthropics, listed in Composio Document Processing), and the superpowers set (obra/superpowers: brainstorming, test-driven-development, verification-before-completion) already fetched separately.
