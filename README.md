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

## PDF エクスポート

```bash
# システムの Chrome を使用してエクスポート（フォント埋め込み対応）
cd slides/<slide-name>
pnpm slidev export --executable-path /usr/bin/google-chrome --output <slug>.pdf
```

### 必要なフォント

PDF エクスポートでフォントが正しく表示されるよう、以下のフォントをシステムにインストールしてください：

```bash
# Ubuntu/Debian
sudo apt install fonts-noto-cjk fonts-noto-color-emoji fonts-open-sans
fc-cache -fv
```

## 構成

```
talks/
├── slides/     # スライドデッキ
├── themes/     # ローカルテーマ
└── .github/    # GitHub Actions
```
