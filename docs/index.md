---
layout: home
title: GitHub Copilot カスタムエージェント実践チュートリアル
---

# GitHub Copilot カスタムエージェント実践チュートリアル

GitHub Copilot の **Custom Agents (`.github/agents/*.agent.md`)** を、基礎から実践まで学ぶ日本語教材です。

- 🌐 GitHub Repository: [duwenji/github-copilot-custom-agents-tutorial](https://github.com/duwenji/github-copilot-custom-agents-tutorial)
- 📦 EPUB 出力: `ebook-output/github-copilot-custom-agents-tutorial.epub`
- ✅ 検証済み: `npm run ebook:build`

---

## 学習ガイド

### Part 0: 基礎準備
- [`.agent.md` の位置づけ](00-fundamentals/00-agent-format-overview.md)
- [Customization Map](00-fundamentals/04-customization-map.md)

### Part 1: 基礎編
- [カスタムエージェントとは](01-basics/01-introduction.md)
- [Skills との違い](01-basics/02-vs-skills.md)
- [カスタムエージェントの動き方](01-basics/03-how-custom-agents-work.md)

### Part 2: 比較編
- [通常プロンプトとの違い](02-comparison/01-vs-prompts.md)
- [Skills / MCP との違い](02-comparison/02-vs-skills-and-mcp.md)
- [どれを選ぶべきか](02-comparison/03-selection-guide.md)

### Part 3: 実装編
- [最初のエージェントを作る](03-implementation/01-getting-started.md)
- [エージェント定義の読み方](03-implementation/02-agent-structure.md)
- [Agent をどう評価するか](03-implementation/06-agent-evaluation.md)
- [Release Prep + Skill 連携](03-implementation/07-sample-release-prep-agent.md)

### Part 4: 運用編
- [ベストプラクティスとアンチパターン](04-operations/01-best-practices.md)
- [Packaging と公開準備](04-operations/03-packaging-and-publishing.md)
- [公開前チェックリスト](04-operations/04-release-checklist.md)
- [FAQ](04-operations/05-faq.md)

### Part 5: 発展編
- [Subagents と Handoffs](05-advanced-topics/01-subagents-and-handoffs.md)
- [チーム向け設計パターン](05-advanced-topics/02-team-design-patterns.md)
- [Orchestrator Agent の例](05-advanced-topics/03-orchestrator-example.md)

---

## サンプルエージェント

- `docs-writer.agent.md`
- `debug-helper.agent.md`
- `repo-maintainer.agent.md`
- `tutorial-orchestrator.agent.md`
- `release-prep.agent.md`

## サンプル Skill

- `release-readiness/SKILL.md`
