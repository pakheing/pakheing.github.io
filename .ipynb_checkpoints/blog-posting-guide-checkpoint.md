---
name: Blog posting guide
description: Standard structure and workflow for creating blog posts on pakheing.github.io
type: reference
originSessionId: 2c848e07-6d29-4fb9-ade2-65fca7d02f66
---
## Blog Post Standard Structure

### File location
All posts go in: `/home/users/s1155191915/work/web/_posts/`

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

### Git push setup
Remote requires token auth. Push workflow:
```bash
git remote set-url origin https://pakheing:<TOKEN>@github.com/pakheing/pakheing.github.io.git
git push
git remote set-url origin https://github.com/pakheing/pakheing.github.io.git
```

### Site details
- Site URL: https://pakheing.github.io
- Repo: pakheing/pakheing.github.io (public)
- Branch: main
- Blog listing page: _pages/blog.md
- Post layout: _layouts/post.html
