# Part 0: `.agent.md` の位置づけ

## 概要

GitHub Copilot の **カスタムエージェント**は、特定の役割に合わせて振る舞いを定義した専用アシスタントです。  
通常の都度プロンプトよりも、**役割・境界・利用ツール**を安定して共有しやすいのが特徴です。

---

## どこに置くのか

ワークスペース単位では、通常次の場所に配置します。

```text
.github/agents/*.agent.md
```

例:

```text
.github/agents/docs-writer.agent.md
.github/agents/debug-helper.agent.md
```

---

## 何を定義するのか

`.agent.md` では主に以下を定義します。

| 項目 | 役割 |
|------|------|
| `description` | いつ使う agent かを示す説明 |
| `tools` | 使ってよいツールの範囲 |
| `model` | 必要に応じて使いたいモデル |
| `agents` | 呼び出せる subagent の制御（必要な場合のみ） |
| 本文 | 役割、制約、手順、出力形式 |

> `agents` は **任意** です。利用可能な agent 名は環境依存なので、必要なければ省略して問題ありません。

---

## 最小サンプル

```md
---
description: "Use this agent when improving README files or markdown documentation."
tools: [read, edit, search]
user-invocable: true
---

You are a documentation-focused Copilot agent.

## Constraints
- Keep edits concise
- Preserve technical accuracy
- Do not modify unrelated files
```

---

## 他のカスタマイズとの違い

| 種類 | 向いている用途 |
|------|----------------|
| `copilot-instructions.md` | リポジトリ全体に共通する指示 |
| `*.prompt.md` | 単発の定型依頼 |
| `SKILL.md` | 再利用できる作業手順 |
| `*.agent.md` | 役割・制約・ツールを持つ専用エージェント |

> 迷ったら、**全体ルールは instructions、単発テンプレは prompt、手順化は skill、役割化は agent** と考えると整理しやすいです。
