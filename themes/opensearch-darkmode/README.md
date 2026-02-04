# slidev-theme-opensearch-template-darkmode

Slidev theme generated from PowerPoint template.

## Local Preview

```bash
cd slidev-theme-opensearch-template-darkmode
pnpm install
pnpm run dev
```

This runs Slidev with `theme: ./` for local development.

## Global Installation

For use across multiple projects:

```bash
# Copy to global themes directory
cp -r slidev-theme-opensearch-template-darkmode ~/.slidev/themes/slidev-theme-opensearch-template-darkmode
cd ~/.slidev/themes/slidev-theme-opensearch-template-darkmode
pnpm install
```

Then in your Slidev project:

```bash
# Create project
mkdir my-slides && cd my-slides

# Initialize
cat > package.json << 'EOF'
{
  "name": "slidev-project",
  "private": true,
  "scripts": {
    "dev": "slidev",
    "build": "slidev build",
    "export": "slidev export"
  }
}
EOF

# Install Slidev and theme
pnpm add @slidev/cli @slidev/theme-default ~/.slidev/themes/slidev-theme-opensearch-template-darkmode
```

Set theme in `slides.md`:

```yaml
---
theme: "slidev-theme-opensearch-template-darkmode"
---
```

## Commands

- `pnpm run dev` - Start dev server
- `pnpm run build` - Build for production
- `pnpm run export` - Export to PDF

## Kiro Skill

Install the Kiro skill for AI-assisted slide creation:

```bash
cp -r skills/slidev-theme-opensearch-template-darkmode ~/.kiro/skills/
```
