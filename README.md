# cv

> CV auto-generated as PDF from Markdown, via Pandoc + WeasyPrint + GitHub Actions.

## Structure

```
.
├── cv.md                          # CV source — edit this
├── style.css                      # Dark/developer theme for HTML and PDF
└── .github/
    └── workflows/
        └── build-cv.yml           # Automatic build pipeline
```

## How it works

1. Edit `cv.md` and push to `master`
2. GitHub Actions runs the workflow:
   - Installs Pandoc + WeasyPrint
   - Converts `cv.md` → `cv.html` (with `style.css`)
   - Converts `cv.html` → `cv.pdf` via WeasyPrint
3. The PDF is uploaded as an **artifact** (retained 30 days) and published as a **`latest` Release**

## Local build

```bash
# Install dependencies
sudo apt install pandoc weasyprint          # Debian/Ubuntu
sudo dnf install pandoc python3-weasyprint  # Fedora

# Generate HTML
pandoc cv.md --standalone --css style.css --to html5 -o cv.html

# Generate PDF
weasyprint cv.html cv.pdf
```

## Customisation

- **Content:** edit `cv.md` — use `inline code` for dates/tags, tables for skills.
- **Colours:** change `--accent` in `style.css` (currently `#00b4d8`).
- **Fonts:** adjust `--font-mono` and `--font-body` in `:root`.
- **Print:** the `@media print` block in `style.css` switches the dark theme to white for physical printing.
