# How to deploy this profile

GitHub displays a special README on your profile page when you create a repository
**named exactly the same as your username**. Here is how to do that.

## One-time setup

```bash
# 1. Create a new repository on GitHub with this exact name (must match your username)
#    → https://github.com/new
#    → Repository name: zhu1090093659
#    → Public, initialize with NO readme
#    → Create.

# 2. Clone it locally
git clone https://github.com/zhu1090093659/zhu1090093659.git
cd zhu1090093659

# 3. Copy the files from this package
#    README.md  →  ./README.md
#    assets/    →  ./assets/
mkdir -p assets
cp /path/to/hero-card.svg     assets/
cp /path/to/journey-map.svg   assets/
cp /path/to/artifacts.svg     assets/
cp /path/to/spellbook.svg     assets/
cp /path/to/README.md         ./

# 4. Commit and push
git add .
git commit -m "feat: pixel-art DQ-style profile"
git push origin main
```

Then visit `https://github.com/zhu1090093659` — the README will render on your profile page.

## File layout

```
zhu1090093659/
├── README.md
└── assets/
    ├── hero-card.svg
    ├── journey-map.svg
    ├── artifacts.svg
    └── spellbook.svg
```

## Editing tips

- Level / HP / MP numbers: edit `hero-card.svg` directly — the values live in plain `<text>` tags.
- Star counts in `artifacts.svg`: same — edit the numbers in the gold boxes when the counts change.
- Spellbook: add a new spell by copying any spell-row pattern in `spellbook.svg` and pasting it in.
- Stats widgets: the three in the README call out to external services
  (`github-readme-stats.vercel.app` and `streak-stats.demolab.com`). Colors already match the
  DQ palette via URL parameters. Nothing to install.

## Local preview

Open `preview.html` in a browser before committing. It shows every chapter inline and
renders the SVGs exactly as GitHub will render them.

## Updating the story later

Anything inside a `<pre><code>` block in the README (the boxed text between chapters)
is just plain text — edit freely. The only thing to preserve is the box-drawing
characters: `╔ ═ ╗ ║ ╚ ╝ ┌ ─ ┐ │ └ ┘`. Keep them aligned by counting columns.
