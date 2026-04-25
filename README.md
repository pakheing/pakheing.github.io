# Pakhei NG — Personal Website

A minimal academic personal website built with Jekyll and deployed on GitHub Pages.

## Quick Start

### 1. Create the GitHub repository

```bash
# On your local machine
git init
git add .
git commit -m "Initial site setup"
git branch -M main
git remote add origin https://github.com/pakheing/pakheing.github.io.git
git push -u git remote add origin https://github.com/pakheing/pakheing.github.io.git
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

Place a square photo at `assets/img/photo.jpg`. Recommended size: 400x400px or larger.

### 4. Add your CV PDF

The CV source is `assets/files/cv.tex`. To recompile:

```bash
cd assets/files
pdflatex -interaction=nonstopmode cv.tex
rm -f cv.log cv.aux cv.out
```

**Important:** Always delete `.log`, `.aux`, and `.out` files after compiling. Only `cv.tex`, `cv.pdf`, and `fullpage.sty` should remain in `assets/files/`.

## Site Details

- **Site URL:** https://pakheing.github.io
- **Repo:** pakheing/pakheing.github.io (public)
- **Branch:** main
- **Push requires token auth** (see Git Push Workflow below)

## Updating Content

| What | Where |
|------|-------|
| Site config (title, email, socials) | `_config.yml` |
| Home page | `_layouts/home.html` and `index.md` |
| About page | `_pages/about.md` |
| CV | `assets/files/cv.tex` and `assets/files/cv.pdf` |
| Research page | `_pages/research.md` |
| Blog posts | `_posts/YYYY-MM-DD-title.md` |
| Styling | `assets/css/style.css` |

## Blog Posts

### File location
All posts go in: `_posts/`

### File naming
`YYYY-MM-DD-title-with-hyphens.md`

### Front matter template
```markdown
---
layout: post
title: "Post Title Here"
date: YYYY-MM-DD
categories: [category1, category2]
---
```

### Available categories
- `general` — personal updates, website news
- `economics` — economics topics, thoughts
- `econometrics` — econometrics methods, analysis
- `r` — R programming tips, tutorials
- `stata` — Stata tips, tutorials
- `research` — research notes, paper discussions
- `coursework` — course-related notes

### Posting workflow
1. User provides: title, content (or notes/ideas), and optionally date
2. Create the `.md` file in `_posts/` with correct naming and front matter
3. `git add _posts/YYYY-MM-DD-title.md && git commit -m "Add blog post: [title]" && git push`
4. Site auto-rebuilds on GitHub Pages within 1-2 minutes

## Git Push Workflow

Remote requires token auth. Push workflow:

```bash
git remote set-url origin https://pakheing:<TOKEN>@github.com/pakheing/pakheing.github.io.git
git push
git remote set-url origin https://github.com/pakheing/pakheing.github.io.git
```

The token is stored in Claude's memory for automated pushes.

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
│   ├── research.md
│   └── blog.md
├── _posts/              # Blog posts
├── assets/
│   ├── css/style.css    # Main stylesheet
│   ├── img/             # Photos and favicon
│   └── files/           # cv.tex, cv.pdf, fullpage.sty
├── Gemfile              # Ruby dependencies
└── index.md             # Homepage
```
