# Contributing

このリポジトリへの改善提案や修正は歓迎です。

## セットアップ

```powershell
git clone --recursive https://github.com/duwenji/github-copilot-custom-agents-tutorial.git
cd github-copilot-custom-agents-tutorial
npm install
```

既に clone 済みの場合は、submodule を更新してください。

```powershell
git submodule update --init --recursive
```

## 変更前の確認

以下のコマンドが通ることを推奨します。

```powershell
npm run quiz:validate
npm run ebook:build
```

## 変更方針

- `Custom Agents` と `Skills` を混同しない
- 初学者向けの日本語を優先する
- サンプル `.agent.md` は単一責務を守る
- 不必要にツール権限を広げない

## Pull Request

PR では次を確認してください。

- リンク切れがない
- 用語が一貫している
- quiz / ebook の導線が崩れていない
- 変更理由が要約されている
