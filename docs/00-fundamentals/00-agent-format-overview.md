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
| `tools` | 使ってよいツールの範囲（= 利用できる機能・権限） |
| `model` | 必要に応じて使いたいモデル |
| `agents` | 呼び出せる subagent の制御（必要な場合のみ） |
| 本文 | 役割、制約、手順、出力形式 |

> `agents` は **任意** です。利用可能な agent 名は環境依存なので、必要なければ省略して問題ありません。

---

## `tools` は何を表すのか

`tools` は、Custom Agent 自身が `.agent.md` の中で実装する関数名ではありません。  
これは **GitHub Copilot / VS Code 側が提供するツールランタイムのうち、その agent に使わせてよい機能・権限を宣言する設定** です。

たとえば `tools: [read, edit, search]` は、
「この agent はファイルを読み、検索し、必要に応じて編集してよい」という意味になります。

### よく使う `tools` の例

| `tools` の例 | できること | 向く場面 |
|--------------|------------|----------|
| `read` | ファイルや内容を読む | 仕様確認、ドキュメント読解 |
| `search` | ワークスペース内を検索する | 関連箇所の調査、影響範囲確認 |
| `edit` | ファイルを編集する | ドキュメント修正、軽微なコード変更 |
| `execute` | コマンドを実行して確認する | デバッグ、ビルド、検証 |
| `todo` | 作業の手順を整理する | 複数ステップの作業管理 |
| `agent` | 別の subagent を呼ぶ | 役割分担、調査の切り分け |

> この一覧は代表例です。実際に利用できる `tools` は **環境やバージョンによって異なる** 場合があります。  
> 内部では `read_file` のような具体的なツールにマッピングされますが、`.agent.md` では **カテゴリとしての許可範囲** を書けば十分です。

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
