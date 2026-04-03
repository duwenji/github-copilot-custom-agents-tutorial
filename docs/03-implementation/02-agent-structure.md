# Part 3-2: エージェント定義の読み方

## 典型的な構成

```md
---
description: "Use this agent when investigating bugs, runtime errors, or broken builds."
tools: [read, search, execute]
user-invocable: true
---

You are a debugging-focused Copilot agent.

## Role
- Investigate failures
- Trace root cause

## Constraints
- Do not guess
- Verify before claiming success

## Approach
1. Read the error
2. Search relevant files
3. Verify the cause

## Output Format
- Summary
- Root cause
- Fix
- Evidence
```

---

## frontmatter の見方

| 項目 | 意味 |
|------|------|
| `description` | いつ使うかを示す説明 |
| `tools` | 使ってよいツール |
| `user-invocable` | 手動選択できるか |
| `model` | 必要に応じて使いたいモデル |
| `agents` | 呼び出せる subagent の制御 |

---

## 本文で差が出るポイント

### 1. Role
この agent の中心責務を短く定義します。

### 2. Constraints
「何をしないか」を明示します。

### 3. Approach
手順を 3〜5 ステップ程度に絞ります。

### 4. Output Format
返答の形を固定すると、利用者が扱いやすくなります。

---

## よくある失敗

- `description` が曖昧
- `tools` を入れすぎる
- 役割が複数混ざる
- 出力形式が毎回ぶれる
