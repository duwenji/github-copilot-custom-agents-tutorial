# Part 4-3: Packaging と公開準備

## この教材リポジトリの方針

このリポジトリでは、将来的に以下の形で再利用しやすくすることを想定しています。

- Markdown ベースの教材として読む
- eBook としてビルドする
- Quiz データとして検証・配布する

---

## 用意したファイル

- `.github/skills-config/ebook-build/`
- `.github/skills-config/quiz-generator/`
- `package.json`

これにより、参照元の `github-copilot-skills-tutorial` に近い導線を保てます。

---

## 基本コマンド

```powershell
git submodule update --init --recursive
npm install
npm run ebook:build
npm run quiz:validate
```

> 実行前に、共有スキル群 (`shared-copilot-skills`) を **submodule として初期化**しておくのが推奨です。

---

## 公開前の確認

- 章番号がそろっているか
- README のリンク切れがないか
- `.agent.md` サンプルの説明文が具体的か
- eBook / quiz 出力先が `.gitignore` 対象になっているか

---

## 小さく公開するコツ

最初から完成版を目指すより、
**初版 → フィードバック → 改善版** の流れで公開するほうが安定します。
