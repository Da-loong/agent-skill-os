---
name: software-engineering-assistant
version: "1.0.0"
display_name: 软件工程助手
display_name_en: Software Engineering Assistant
description: 软件工程助手，做真实工程不是vibe coding。按网站介绍整合4个真实skill修4个失败模式：grill-me对齐需求、frontend-design定视觉方向、tdd红绿循环做功能、changelog-generator把提交变成用户更新日志。4个阶段共享同一份spec、glossary、seams和提交记录，前一阶段的产出就是后一阶段的输入。
description_zh: 软件工程助手，做真实工程不是vibe coding。按网站介绍整合4个真实skill修4个失败模式：grill-me对齐需求、frontend-design定视觉方向、tdd红绿循环做功能、changelog-generator把提交变成用户更新日志。4个阶段共享同一份spec、glossary、seams和提交记录，前一阶段的产出就是后一阶段的输入。
description_en: Software Engineering Assistant, for real engineering not vibe coding. It integrates 4 real skills from their own introductions to fix 4 failure modes: grill-me aligns the requirement, frontend-design sets the visual direction, tdd builds test-first in red-green loops, changelog-generator turns commits into user changelogs. The 4 stages share one spec, glossary, seams list and commit history, and each stage output is the next stage input.
---

# 软件工程助手

## 这不是合集，是什么

来源网站的介绍已经把目的说清楚了，不是星高就往一起堆：

- mattpocock/skills 的介绍说，这些 skill 是为了解决用 coding agent 时常见的失败模式，口号是做真实工程，不是 vibe coding。
- 失败模式 1 是 agent 没做用户想要的，原因是没对齐，修法是 grilling。
- 失败模式 3 是代码跑不起来，原因是没有反馈循环，修法是红绿测试循环。
- frontend-design 的介绍说，先定一个具体的视觉方向再写代码，不要出紫色渐变加 Inter 字体的模板默认。
- Composio 清单里 changelog-generator 的介绍说，把技术提交翻译成用户能看懂的更新日志。

所以这个包只做一件事：**从一个想法出发，做出一个能跑、能看、能发版的网页功能**。不在这件事里的 skill，即使星高也砍掉。下面砍掉的和原因写在最后。

## 共享产物（整合的关键，不共享就不叫整合）

整个流程只维护 4 份产物，后一阶段不许重编前一阶段的东西：

1. `SPEC.md`：grill 阶段产出，写清要做什么、为什么、目标、非目标、反目标。
2. `GLOSSARY.md`：grill 阶段产出，写清项目专有词，一个词一个意思，测试名、变量名、界面文案都用这里的词。
3. `SEAMS.md`：grill 阶段和 tdd 阶段共同确认，写清要测试的公开边界，每个 seam 一行，写清它测什么、测不到什么。没有确认的 seam 不写测试。
4. `AESTHETIC.md`：frontend-design 阶段产出，写清配色、字体搭配、布局、动效，以及明确不用的模板默认。
5. git 提交记录：tdd 阶段产出，提交信息写清改了什么，供 changelog 阶段直接用。

## 四个阶段，按顺序，不许跳

### 阶段 1：对齐 — grill-me（mattpocock/skills）

原文介绍：Relentless interviewing skill that stress-tests plans and designs through systematic questioning. Designed for design reviews, architecture validation, and pre-implementation planning where thorough vetting prevents downstream issues.

做法按 references/grill-me.md 和源仓库的 grilling 会话来：
- 一轮只问一个决策树分支，走完一个分支再走下一个，直到对齐。
- 每个问题都要具体到这个项目，不要问通用问题。
- 产出 SPEC.md、GLOSSARY.md、SEAMS.md 初稿，并让用户确认。
- 没有用户确认的 spec，不进下一阶段。用户说“直接做吧”才算跳过对齐，且要把这个选择写进 SPEC.md。

注意：grill-me 原文 SKILL.md 本身只有 157 字节，写的是 Call the Skill tool with "grilling"，完整会话在源仓库，不要把这个 stub 编成完整流程。

### 阶段 2：定视觉 — frontend-design（anthropics/skills，只做界面部分）

原文介绍：Guidance for distinctive, intentional visual design when building new UI or reshaping an existing one. Helps with aesthetic direction, typography, and making choices that don't read as templated defaults.

做法按 references/frontend-design.md 来：
- 先定视觉方向，再写一行界面代码。
- 产出 AESTHETIC.md，写清配色、字体、布局、动效，以及为什么是这个方向。
- 非界面任务跳过本阶段，不要硬套设计。

### 阶段 3：做功能 — tdd（mattpocock/skills）

原文介绍：TDD is the red → green loop. This skill is the reference that makes that loop produce tests worth keeping: what a good test is, where tests go, the anti-patterns, and the rules of the loop. Tests verify behavior through public interfaces, not implementation details.

做法按 references/tdd.md 来：
- 只在 SEAMS.md 里已确认的 seam 上写测试，没有确认的 seam 不写。
- 测试名用 GLOSSARY.md 里的词，测试只测公开行为，不测内部实现。
- 红绿循环：先写失败测试，看它失败，再写最少实现让它通过，再重构，重构后仍要全绿。
- 没有失败测试在先，不写生产代码。

### 阶段 4：发版 — changelog-generator（ComposioHQ/awesome-claude-skills）

原文介绍：Automatically creates user-facing changelogs from git commits by analyzing commit history, categorizing changes, and transforming technical commits into clear, customer-friendly release notes.

做法按 references/changelog-generator.md 来：
- 输入就是阶段 3 的 git 提交记录，不要重编改了什么。
- 分类：功能、改进、修 bug、破坏性变更、安全。
- 输出是用户语言的更新日志，不是技术提交原样。

## 完成标准（按原文，不自编）

- SPEC.md、GLOSSARY.md、SEAMS.md 都有用户确认记录，否则不算对齐完成。
- 每个功能都有先失败后通过的测试记录，否则不算做完。
- 界面有 AESTHETIC.md 且实现与之对应，否则不算设计完成。
- 更新日志的每一条都能对应到一个提交，否则不算发版完成。

## 砍掉的 skill 和原因（整合的一部分）

- find-skills（vercel-labs/skills）：它是发现其他 skill 的元 skill，在这个已经定好的流程里没有位置，留着只会让 agent 每次都先去找 skill，偏离流程，所以砍掉。
- 上一批里的其他高星 skill：不在“想法到发版”这条链上，或者和上面 4 个触发条件、输出格式冲突的，这次都不放进来。星高不是放进来的理由。
