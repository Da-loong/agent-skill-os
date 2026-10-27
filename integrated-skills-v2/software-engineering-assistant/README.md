# 软件工程助手

v2 真整合包，不是 v1 那种合集。

## 目的（从网站介绍读出来的）

做真实工程，不是 vibe coding。从一个想法出发，做出能跑、能看、能发版的网页功能。

## 四个阶段和交接

1. grill-me 对齐 → 产出 SPEC.md、GLOSSARY.md、SEAMS.md
2. frontend-design 定视觉 → 产出 AESTHETIC.md（只做界面部分）
3. tdd 做功能 → 只在已确认的 seam 上红绿循环，产出 git 提交
4. changelog-generator 发版 → 输入就是上面的提交，产出用户更新日志

## 砍掉的

- find-skills：元 skill，不在流程里，砍掉。
- 不在想法到发版链上的高星 skill：这次不放。

## GitHub

先推 GitHub 再打包，见仓库 Da-loong/agent-skill-os，分支 integrated-skills-v2，目录 integrated-skills-v2/。

## WorkBuddy 上传

- 直接传打包好的 zip，平台自动解包并生成技能 ID
- 解包后第一层就是 software-engineering-assistant 文件夹，里面直接有 SKILL.md
- frontmatter 已补齐 version、display_name、display_name_en、description_zh、description_en
