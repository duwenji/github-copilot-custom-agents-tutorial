# Part 4-1: ベストプラクティスとアンチパターン

## ベストプラクティス

### 1. 単一責務にする
- 1つの agent に 1つの中心的役割を持たせる
- docs 用、debug 用、review 用を分ける

### 2. `description` を具体的にする
- 「いつ使うか」を文章で書く
- README、debug、broken build などのキーワードを含める

### 3. `tools` は最小限にする
- まず read-only に近い構成から始める
- 実行や編集は必要な agent にだけ許可する

### 4. 出力形式を固定する
- summary
- root cause
- next action
- evidence

### 5. Agent と Skill を混ぜすぎない
- Agent は**役割**に集中させる
- Skill は**再利用手順**に集中させる
- 毎回同じ確認フローを書くなら Skill 側へ寄せる

---

## アンチパターン

### Swiss-army agent
何でもできる 1体にしようとして、責務が曖昧になるパターンです。

### 曖昧な description
`"Helpful assistant"` のような説明では役割が伝わりません。

### ツール過多
最初から `execute`, `edit`, `web`, `agent` を全部入れると、設計がぶれやすくなります。

### 検証なしの完了宣言
特に debug 系 agent で危険です。実行結果やテスト確認を伴うべきです。

---

## 推奨レビュー観点

- この agent の責務は一文で説明できるか
- 許可ツールは本当に必要最小限か
- 使う場面と使わない場面が明確か
- 出力形式が利用者にとって一貫しているか
