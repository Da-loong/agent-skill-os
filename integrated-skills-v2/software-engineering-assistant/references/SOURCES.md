# Sources — v2 real integration

This package was built by reading the introductions on the two sites the user gave, not by stacking stars.

## skills.sh

- https://skills.sh/ — leaderboard, All Time
- grill-me — mattpocock/skills — skills.sh page says: "Relentless interviewing skill that stress-tests plans and designs through systematic questioning." and "Designed for design reviews, architecture validation, and pre-implementation planning where thorough vetting prevents downstream issues." Original SKILL.md path skills/productivity/grill-me/SKILL.md, SHA 3947ff9c4ad980d14fc07fccbf659d47c114e81d, 157 bytes, stub calling "grilling".
- tdd — mattpocock/skills — skills.sh page says: "TDD is the red → green loop. This skill is the reference that makes that loop produce tests worth keeping" and "Tests verify behavior through public interfaces, not implementation details." Original SKILL.md path skills/engineering/tdd/SKILL.md, SHA 01eadaa34e7c9a63a67d6dc3cce1cc81b0e49985.
- frontend-design — anthropics/skills — introduction says: "A skill for building frontend interfaces with intentional aesthetic direction. It pushes past generic patterns by committing to a specific visual tone before writing a line of code" and "Instead of producing the same purple-gradient-on-white output most AI tools default to". Original SKILL.md path skills/frontend-design/SKILL.md, SHA a5333457c414d20d625f307df945842c0952ecc3.
- mattpocock/skills README, "Why These Skills Exist": failure mode 1 is agent didn't do what you want, fix is grilling; failure mode 3 is code doesn't work, fix is red-green-refactor feedback loops; tagline is "Skills For Real Engineers" and "not vibe coding".

## ComposioHQ/awesome-claude-skills

- https://github.com/ComposioHQ/awesome-claude-skills — curated list, categories include Document Processing, Development & Code Tools, etc. Skills are described as reusable instruction packages with SKILL.md frontmatter and progressive loading.
- changelog-generator — in-repo skill, path changelog-generator/SKILL.md, SHA 72919de07da6d02a7824309529aefde94a2109dd, description: "Automatically creates user-facing changelogs from git commits by analyzing commit history, categorizing changes, and transforming technical commits into clear, customer-friendly release notes."

## What v2 drops and why

- find-skills is dropped: it is a meta discovery skill, not a stage in idea-to-release, and keeping it would pull the agent off the fixed pipeline.
- v1 batch was a collection, not an integration: 5 skills in one folder with no shared artifacts and no handoff. v2 replaces that approach for this package, it does not claim v1 was an integration.
