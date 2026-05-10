# myOs — acrovia.se Web Hosting Files

Web installation files for [acrovia.se](https://acrovia.se) (osCommerce-based).

## Directory Structure

```
myOs/
├── public_html/          # Main web root (your site files go here)
│   ├── css/              # Stylesheets
│   ├── js/               # JavaScript files
│   ├── images/           # Site images (keep under 100MB total)
│   └── fonts/            # Web fonts
├── config/               # Configuration templates (NO credentials!)
├── scripts/              # Deployment/maintenance scripts
├── .gitignore            # Files excluded from version control
└── README.md             # This file
```

## What to INCLUDE in this repo

| Include | Examples |
|---------|----------|
| HTML/PHP files | `index.php`, templates, pages |
| CSS stylesheets | `style.css`, custom themes |
| JavaScript | `scripts.js`, custom JS |
| Small images | logos, icons, UI graphics (< 100MB each) |
| Font files | `.woff`, `.woff2`, `.ttf` |
| Config templates | `config.example.php` (without real credentials) |
| `.htaccess` | URL rewrites, security rules |
| osCommerce core files | catalog, admin templates |

## What to EXCLUDE (already in .gitignore)

| Exclude | Reason |
|---------|--------|
| `.env`, `config.php` with passwords | Security — never commit credentials |
| `*.sql` database dumps | Too large, use separate backup |
| `node_modules/`, `vendor/` | Reinstall from package manager |
| `*.log` files | Server-generated, not needed |
| Large media (videos, PSD) | Use external hosting or Git LFS |
| `cache/`, `tmp/`, `sessions/` | Server-generated temporary files |
| OS files (`.DS_Store`, `Thumbs.db`) | Not relevant to project |
| Editor files (`.vscode/`, `.idea/`) | Personal preference |

## How to Sync Your Local Files

1. **Clone this repo** to your local machine:
   ```bash
   git clone https://github.com/acrovia-2026/myOs.git
   ```

2. **Copy your website files** into the `public_html/` folder.

3. **Check what will be committed** (make sure no secrets):
   ```bash
   git status
   git diff
   ```

4. **Commit and push**:
   ```bash
   git add .
   git commit -m "Add website files"
   git push origin main
   ```

## Security Reminders

- **NEVER** commit files with database passwords, API keys, or secrets
- Use `config.example.php` as a template, keep real config on server only
- Review `git status` before every commit
- If you accidentally commit a secret, change the password immediately (git history retains old files)

## Git LFS (for large files)

If you have images/media over 50MB, consider Git LFS:
```bash
git lfs install
git lfs track "*.psd"
git lfs track "*.mp4"
```
