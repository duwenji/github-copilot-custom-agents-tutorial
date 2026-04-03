# Part 3-1: 最初のエージェントを作る

## ゴール

ここでは、最小構成のカスタムエージェントを 1 つ作ります。

---

## Step 1: ファイルを作る

次の場所にファイルを作成します。

```text
.github/agents/my-first-docs.agent.md
```

---

## Step 2: 最小 frontmatter を書く

```md
---
description: "Use this agent when improving README files or markdown documentation."
tools: [read, edit, search]
user-invocable: true
---
```

ここで大切なのは次の3つです。

- `description`: いつ使うかを具体的に書く
- `tools`: 最小限に絞る
- `user-invocable`: 手動で使えるようにする

---

## Step 3: 本文を書く

```md
You are a documentation-focused Copilot agent.

## Constraints
- Keep edits concise
- Preserve technical accuracy
- Do not modify unrelated files

## Approach
1. Read the target file
2. Improve clarity and structure
3. Summarize the changes
```

---

## Step 4: 試す

例:

- "README を読みやすく整えて"
- "この教材の説明を初学者向けに短くして"
- "Markdown の見出し構造を改善して"

---

## 最初のチェックリスト

- [ ] `description` が具体的か
- [ ] `tools` を盛りすぎていないか
- [ ] してはいけないことを書いているか
- [ ] 返してほしい出力の形が明確か

最初は完璧を目指さず、**1 role / 1 task** に絞るのが成功のコツです。
