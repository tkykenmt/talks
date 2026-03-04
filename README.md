# Talks

Presentations built with Slidev

## Slides

| Slide | URL |
|-------|-----|
| [OpenSearch 2025-2026 Roadmap](./slides/20260205-opensearch-2025-2026-roadmap/) | [GitHub Pages](https://tkykenmt.github.io/talks/20260205-opensearch-2025-2026-roadmap/) |
| [OpenSearch 2025-2026 Roadmap (EN)](./slides/20260205-opensearch-2025-2026-roadmap-en/) | [GitHub Pages](https://tkykenmt.github.io/talks/20260205-opensearch-2025-2026-roadmap-en/) |

## Development

```bash
# Install dependencies
pnpm install

# Start dev server
pnpm --filter <slide-name> dev

# Example
pnpm --filter 20260205-opensearch-2025-2026-roadmap dev
```

## PDF Export

```bash
# Export using system Chrome (for font embedding)
cd slides/<slide-name>
pnpm slidev export --executable-path /usr/bin/google-chrome --output <slug>.pdf
```

### Required Fonts

Install the following fonts for correct PDF rendering:

```bash
# Ubuntu/Debian
sudo apt install fonts-noto-cjk fonts-noto-color-emoji fonts-open-sans
fc-cache -fv
```

## Structure

```
talks/
├── slides/     # Slide decks
├── themes/     # Local themes
└── .github/    # GitHub Actions
```
