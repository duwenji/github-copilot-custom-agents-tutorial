# Part 1-3: カスタムエージェントの動き方

## 基本フロー

カスタムエージェントは、おおむね次の流れで使われます。

```text
ユーザーの依頼
  ↓
説明文 (`description`) に合う agent が選ばれる
  ↓
agent の役割・制約・利用可能ツールが適用される
  ↓
必要ならファイル読取・検索・編集・実行を行う
  ↓
結果をまとめて返す
```

---

## `description` が重要な理由

`description` は、**いつその agent を使うべきか**を示す入口です。

悪い例:

```yaml
description: "Helpful assistant"
```

良い例:

```yaml
description: "Use this agent when updating README files, markdown guides, or tutorial content."
```

具体的なキーワードがあるほど、役割がぶれにくくなります。

---

## `tools` は絞るほど強い

ツールを増やしすぎると、agent の責務が曖昧になります。

たとえば docs 専用なら:

```yaml
tools: [read, edit, search]
```

デバッグ専用なら:

```yaml
tools: [read, search, execute]
```

> まずは **最小ツールセット** で始め、必要になったら増やすのが安全です。

---

## 本文には何を書くか

本文では次を明確にします。

- **Role**: 何担当か
- **Constraints**: 何をしてはいけないか
- **Approach**: どう進めるか
- **Output Format**: どう返すか

この4点があると、agent の挙動がかなり安定します。
