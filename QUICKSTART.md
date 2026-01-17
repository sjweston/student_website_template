# Quick Start Guide

Get your academic website up and running in 5 minutes!

## 1. Install Prerequisites

Install both Hugo and Go (both are required):

```bash
# macOS
brew install hugo
brew install go

# Windows (using Chocolatey)
choco install hugo-extended
choco install golang

# Linux
sudo apt-get install hugo
sudo apt-get install golang
```

Verify:
```bash
hugo version  # Should show 0.136.5 or higher
go version    # Should show 1.19 or higher
```

## 2. Download Theme Modules

First time only - download the theme:
```bash
hugo mod get -u
```

## 3. Preview Locally

```bash
hugo server
```

Open http://localhost:1313 in your browser.

## 4. Personalize (Minimum Changes)

Edit these 3 files:

### `config/_default/hugo.yaml`
```yaml
title: Your Name
baseURL: 'https://yourusername.github.io/'
```

### `config/_default/params.yaml`
```yaml
header:
  navbar:
    logo:
      text: "Your Name"
```

### `content/authors/admin/_index.md`
- Change `title`, `first_name`, `last_name`
- Update `role` and `organizations`
- Update social media links (email, GitHub, etc.)
- Update research interests, education, work experience
- Write your bio at the bottom

### Replace your photo
Replace `content/authors/admin/avatar.jpg` with your photo.

## 5. Add Your Content

### Publications
Add to `publications.bib` then run:
```bash
python create_pubs.py
```

### Projects
Create folders in `content/project/` (see examples)

### Blog Posts
Create folders in `content/post/` (see examples)

### Teaching
Create folders in `content/teaching/` (see examples)

## 6. Deploy to GitHub Pages

### Option A: Using GitHub Desktop (Easier)
1. Install [GitHub Desktop](https://desktop.github.com/)
2. Create repo on GitHub.com named `yourusername.github.io`
3. In GitHub Desktop: File → Clone Repository → select your repo
4. Copy all your website files into the cloned folder
5. In GitHub Desktop: Commit changes → Push origin

### Option B: Using Terminal
```bash
# Create a repo named: yourusername.github.io on GitHub.com first
git init
git add .
git commit -m "Initial commit"
git branch -M main
git remote add origin https://github.com/yourusername/yourusername.github.io.git
git push -u origin main
```

### Enable GitHub Pages:
1. Go to repo Settings → Pages
2. Under "Source", select "GitHub Actions"
3. Wait 2-3 minutes for deployment
4. Visit `https://yourusername.github.io`

Done! 🎉

For detailed instructions and troubleshooting, see [README.md](README.md).
