# GitHub Copilot カスタムエージェント実践チュートリアル

[![Validate tutorial repo](https://github.com/duwenji/github-copilot-custom-agents-tutorial/actions/workflows/validate.yml/badge.svg)](https://github.com/duwenji/github-copilot-custom-agents-tutorial/actions/workflows/validate.yml)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

GitHub Copilot の **カスタムエージェント (`.github/agents/*.agent.md`)** を、基礎から実践まで学ぶ日本語教材です。

> このリポジトリは `github-copilot-skills-tutorial` を参照しつつ、**Skills ではなく Custom Agents に特化**して再構成した学習用プロジェクトです。

- 🌐 **公開リポジトリ**: https://github.com/duwenji/github-copilot-custom-agents-tutorial
- � **GitHub Pages**: `https://duwenji.github.io/github-copilot-custom-agents-tutorial/`
- �📦 **検証済み出力**: `ebook-output/github-copilot-custom-agents-tutorial.epub`
- 🧩 **共有スキル**: `git submodule update --init --recursive`

---

## この教材で学べること

- カスタムエージェントとは何か
- `copilot-instructions.md` / `prompts` / `skills` / `agents` の違い
- `.agent.md` の基本構造と設計原則
- 実務で使えるエージェント例
- チーム共有・レビュー・運用のベストプラクティス

---

## 想定読者

- GitHub Copilot をこれから本格活用したい開発者
- `Skills` は見たことがあるが `Custom Agents` は未経験の人
- チーム向けの標準エージェントを設計したい担当者

---

## クイックスタート

1. `git clone --recursive https://github.com/duwenji/github-copilot-custom-agents-tutorial.git`
2. `.github/agents/` 配下のサンプルを開く
3. `docs/00-fundamentals/agent-format-overview.md` を読む
4. `docs/03-implementation/01-getting-started.md` に沿って自分の agent を作る
5. 必要なら `npm install` 後に `npm run ebook:build` / `npm run quiz:validate` を使う

現在含まれるサンプル:

- `docs-writer.agent.md` — Markdown/README 改善向け
- `debug-helper.agent.md` — バグ調査と原因分析向け
- `repo-maintainer.agent.md` — リポジトリ整備向け
- `tutorial-orchestrator.agent.md` — 複数ステップ作業の調整役

---

## 目次

### Part 0: 基礎準備
- [Part 0: `.agent.md` の位置づけ](docs/00-fundamentals/agent-format-overview.md)

### Part 1: 基礎編
- [Part 1-1: カスタムエージェントとは](docs/01-basics/01-introduction.md)
- [Part 1-2: Skills との違い](docs/01-basics/02-vs-skills.md)
- [Part 1-3: カスタムエージェントの動き方](docs/01-basics/03-how-custom-agents-work.md)

### Part 2: 比較編
- [Part 2-1: 通常プロンプトとの違い](docs/02-comparison/01-vs-prompts.md)
- [Part 2-2: Skills / MCP との違い](docs/02-comparison/02-vs-skills-and-mcp.md)
- [Part 2-3: どれを選ぶべきか](docs/02-comparison/03-selection-guide.md)

### Part 3: 実装編
- [Part 3-1: 最初のエージェントを作る](docs/03-implementation/01-getting-started.md)
- [Part 3-2: エージェント定義の読み方](docs/03-implementation/02-agent-structure.md)
- [Part 3-3: サンプル1 - Docs Writer](docs/03-implementation/03-sample-docs-agent.md)
- [Part 3-4: サンプル2 - Debug Helper](docs/03-implementation/04-sample-debug-agent.md)
- [Part 3-5: サンプル3 - Repo Maintainer](docs/03-implementation/05-sample-repo-agent.md)
- [Part 3-6: Agent をどう評価するか](docs/03-implementation/06-agent-evaluation.md)

### Part 4: 運用編
- [Part 4-1: ベストプラクティスとアンチパターン](docs/04-operations/01-best-practices.md)
- [Part 4-2: Agent レビュー・チェックリスト](docs/04-operations/02-review-checklist.md)
- [Part 4-3: Packaging と公開準備](docs/04-operations/03-packaging-and-publishing.md)
- [Part 4-4: 公開前チェックリスト](docs/04-operations/04-release-checklist.md)

### Part 5: 発展編
- [Part 5-1: Subagents と Handoffs](docs/05-advanced-topics/01-subagents-and-handoffs.md)
- [Part 5-2: チーム向け設計パターン](docs/05-advanced-topics/02-team-design-patterns.md)
- [Part 5-3: Orchestrator Agent の例](docs/05-advanced-topics/03-orchestrator-example.md)

---

## リポジトリ構成

```text
.github/
  agents/
  copilot-instructions.md
docs/
  00-fundamentals/
  01-basics/
  02-comparison/
  03-implementation/
  04-operations/
  05-advanced-topics/
```

---

## GitHub Pages

このリポジトリには `.github/workflows/pages.yml` を含めており、`main` への push で `docs/` を GitHub Pages にデプロイする構成です。

想定 URL:

```text
https://duwenji.github.io/github-copilot-custom-agents-tutorial/
```

---

## 検証済みコマンド

```powershell
npm install
npm run ebook:build
npm run quiz:validate
```

これらは現在のリポジトリで実行確認済みです。

---

## 実装状況

- ✅ 教材の初期骨格を作成
- ✅ サンプルエージェントを4本追加
- ✅ 基礎編・比較編・実装編・運用編・発展編の初版を追加
- ✅ `ebook-build` / `quiz-generator` 向けの設定ファイルを追加
- 🔄 章本文をさらに拡充中
- 🔄 将来的に quiz データや ebook 出力を本格生成予定
