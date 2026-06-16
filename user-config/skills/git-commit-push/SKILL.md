---
name: git-commit-push
description: 当用户说"提交"、"commit"、"push"并附带提交信息时触发。例如"提交 修复登录bug"、"commit add new feature"。执行 git pull → git commit → git push 三步流程。即使用户只说"提交XXX"或"commit XXX"而没有明确提到push，也应使用此skill。
---

# Git Commit & Push 工作流

当用户说"提交 XXXXX"或"commit XXXXX"时，按以下顺序执行三步操作：

## 步骤

1. **git pull** — 先拉取远程最新代码，避免冲突
2. **git add + git commit** — 暂存所有变更，用用户提供的内容作为 commit message
3. **git push** — 推送到远程仓库

## 规则

- 提交信息直接使用用户说的内容，不需要加前缀或修改
- 如果 git pull 出现冲突，停下来告知用户，不要继续 commit 和 push
- 如果工作区没有变更，告知用户无需提交
- 不要使用 --no-verify 或 --force 等危险参数
