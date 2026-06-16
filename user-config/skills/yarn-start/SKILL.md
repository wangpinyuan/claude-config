---
name: yarn-start
description: 当用户说"启动项目"、"启动"、"start"、"yarn start"、"运行项目"时触发。执行 git pull → yarn install → yarn start 三步流程。即使用户只说"启动"而没有提到完整的步骤，也应使用此skill。
---

# Yarn Start 工作流

当用户说"启动项目"、"启动"、"start"等时，按以下顺序执行三步操作：

## 步骤

1. **git pull** — 拉取远程最新代码
2. **yarn install** — 安装/更新依赖
3. **yarn start** — 启动项目

## 规则

- 如果 git pull 出现冲突，停下来告知用户，不要继续后续步骤
- 如果 yarn install 失败，停下来告知用户，不要执行 yarn start
- 按顺序执行，前一步成功后才执行下一步
