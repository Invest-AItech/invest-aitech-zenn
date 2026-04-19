# invest-aitech-zenn

Zenn 投稿用リポジトリ。`main` ブランチへの push で [Zenn Connect](https://zenn.dev/dashboard/deploys) が自動取り込みする。

## 構成

```
articles/<slug>.md   # 記事本体（フロントマターつき）
books/               # 本（未使用）
package.json         # zenn-cli 依存
```

正本は `invest_aitech/30_publishing/articles/<slug>/article.md`。このリポジトリの `articles/<slug>.md` は `published/zenn.md` のスナップショット。

## 公開フロー

1. 30_publishing 側で `article.md` を完成させる
2. `published/zenn.md` をフロントマター付きで用意（`published: false` で下書きとして）
3. 本リポジトリの `articles/<slug>.md` にコピー → commit → push
4. Zenn ダッシュボードで取り込み確認
5. レビュー OK 後、`published: true` に変更して push → 即公開

## ローカルプレビュー

```bash
npx zenn preview
```

http://localhost:8000 で確認。

## Zenn CLI Docs

- [How to use Zenn CLI](https://zenn.dev/zenn/articles/zenn-cli-guide)
