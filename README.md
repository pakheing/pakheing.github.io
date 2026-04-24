# Pakhei NG — Personal Website

A minimal academic personal website built with Jekyll and deployed on GitHub Pages.

## Quick Start

### 1. Create the GitHub repository

```bash
# On your local machine (or on SCRP)
git init
git add .
git commit -m "Initial site setup"
git branch -M main
git remote add origin https://github.com/pakheing/pakheing.github.io.git
git push -u origin main
```

If the repo name `pakheing.github.io` is taken, you can use any name (e.g. `personal-site`) and enable GitHub Pages in the repo Settings > Pages.

### 2. Enable GitHub Pages

1. Go to your repo on GitHub
2. Click **Settings** > **Pages**
3. Under **Source**, select **Deploy from a branch**
4. Choose **main** branch and **/ (root)** folder
5. Click **Save**

Your site will be live at `https://pakheing.github.io` within a few minutes.

### 3. Add your profile photo

Place a square photo at `assets/img/photo.jpg`. Recommended size: 400×400px or larger.

### 4. Add your CV PDF

Place your CV at `assets/files/cv.pdf`. The CV page links to this file for download.

## Updating Content

| What | Where |
|------|-------|
| Site config (title, email, socials) | `_config.yml` |
| Home page | `_layouts/home.html` and `index.md` |
| About page | `_pages/about.md` |
| CV page | `_pages/cv.md` and `assets/files/cv.pdf` |
| Research page | `_pages/research.md` |
| Blog posts | `_posts/YYYY-MM-DD-title.md` |
| Styling | `assets/css/style.css` |

### Writing a new blog post

Create a file in `_posts/` with the naming format `YYYY-MM-DD-title.md`:

```markdown
---
layout: post
title: "My New Post"
date: 2026-05-01
categories: [economics]
---

Your content here.
```

Commit and push — GitHub Pages will rebuild automatically.

## Local Preview (Optional)

If you want to preview changes before pushing:

```bash
# Install dependencies (one-time)
bundle install

# Serve locally
bundle exec jekyll serve
```

Then open `http://localhost:4000` in your browser.

## Structure

```
├── _config.yml          # Site configuration
├── _layouts/            # Page templates
│   ├── default.html     # Main layout with header/footer
│   ├── home.html        # Homepage layout
│   ├── page.html        # Generic page layout
│   └── post.html        # Blog post layout
├── _pages/              # Static pages
│   ├── about.md
│   ├── cv.md
│   ├── research.md
│   └── blog.md
├── _posts/              # Blog posts
├── assets/
│   ├── css/style.css    # Main stylesheet
│   ├── img/             # Photos and favicon
│   └── files/           # PDFs (CV, etc.)
├── Gemfile              # Ruby dependencies
└── index.md             # Homepage
```
