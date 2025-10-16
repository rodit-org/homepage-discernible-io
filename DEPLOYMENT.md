# Deployment Guide

## Overview

This repository automatically deploys to Apache web server at `/var/www/domains/discernible.io/public_html/` on every git commit.

## Automatic Deployment

### Setup (Already Configured)
- ✅ Git post-commit hook installed at `.git/hooks/post-commit`
- ✅ Deployment script created at `deploy.sh`
- ✅ Apache configured to serve from `/var/www/domains/discernible.io/public_html/`

### How to Use
Simply commit your changes and they will automatically deploy:

```bash
# Make your changes to files in public/
vim public/index.html

# Commit your changes
git add .
git commit -m "Update homepage content"

# Deployment happens automatically!
```

## Manual Deployment

If you need to deploy without committing:

```bash
./deploy.sh
```

## Troubleshooting

### Check deployment logs
```bash
tail -f deploy.log
```

### Verify files are deployed
```bash
ls -la /var/www/domains/discernible.io/public_html/
```

### Check Apache status
```bash
sudo systemctl status apache2
```

### Reload Apache manually
```bash
sudo systemctl reload apache2
```

### Test with curl (bypass browser cache)
```bash
curl -I https://discernible.io/
```

## Color Scheme

The website uses the brand colors from the discernible.io logo:

- **Primary (Orange)**: `#FF4500`
- **Secondary (Black)**: `#000000`
- **Accent (Light Orange)**: `#FF6B35`
- **White**: `#FFFFFF`

These are defined in `public/styles.css` under the `:root` selector.

## File Structure

```
/home/icarus40/homepage-discernible-io/  (Development)
└── public/
    ├── index.html
    ├── styles.css
    ├── script.js
    └── .htaccess

/var/www/domains/discernible.io/public_html/  (Production)
└── (Same files as above, deployed automatically)
```

## Important Notes

1. **Always edit files in `/home/icarus40/homepage-discernible-io/public/`**, not in the Apache directory
2. **Commit your changes** to trigger automatic deployment
3. **Check deploy.log** if something doesn't work
4. The `.htaccess` file disables caching during development (remove for production)
