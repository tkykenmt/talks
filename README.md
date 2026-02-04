# Talks

Slidev を使ったプレゼンテーション集

## スライド一覧

| スライド | 公開URL |
|----------|---------|
| [OpenSearch 2025-2026 Roadmap](./slides/20260205-opensearch-2025-2026-roadmap/) | [GitHub Pages](https://tkykenmt.github.io/talks/20260205-opensearch-2025-2026-roadmap/) |

## 開発

```bash
# 依存関係インストール
pnpm install

# 開発サーバー起動
pnpm --filter <slide-name> dev

# 例
pnpm --filter 20260205-opensearch-2025-2026-roadmap dev
```

## 構成

```
talks/
├── slides/     # スライドデッキ
├── themes/     # ローカルテーマ
└── .github/    # GitHub Actions
```
