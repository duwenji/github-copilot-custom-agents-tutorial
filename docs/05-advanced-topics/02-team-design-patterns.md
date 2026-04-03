# Part 5-2: チーム向け設計パターン

## 目的別の分け方

チームで運用する場合、agent は次のように分けると整理しやすくなります。

### 1. ロール別
- `docs-writer`
- `debug-helper`
- `repo-maintainer`

### 2. フェーズ別
- 企画用 agent
- 実装支援 agent
- レビュー用 agent

### 3. リスク別
- 読み取り中心の安全な agent
- 編集可能な agent
- 実行権限を持つ agent

---

## 命名のコツ

- 短く、責務がわかる名前にする
- `helper`, `writer`, `reviewer`, `maintainer` など役割語を含める
- 曖昧な名前を避ける

悪い例:
- `smart-agent`
- `ultimate-helper`

良い例:
- `docs-writer`
- `debug-helper`
- `frontend-reviewer`

---

## レビュー観点

- 役割が一文で説明できるか
- `description` が具体的か
- ツール権限が過剰でないか
- 利用者が迷わず選べるか
