+++
date = '2026-02-01'
draft = false
title = 'Build Your Own'
+++

Paste this into your agentic coding tool of choice to set up a personal blog deployed to GitHub Pages.

## What you'll get

- A Hugo static site using the [Weaver](https://github.com/highb/weaver) theme (IndieWeb-friendly)
- GitHub Pages deployment via GitHub Actions
- A ready-to-write blog with posts, an about page, and navigation

## Prerequisites

- Git installed
- A GitHub account with a repo created (can be empty)
- [Hugo extended](https://gohugo.io/installation/) installed locally (for previewing)
- [GitHub CLI (`gh`)](https://cli.github.com/) installed and authenticated

## Prompt

Copy everything below this line and paste it into your LLM coding tool, replacing the placeholder values with your own.

---

I want you to set up a Hugo blog deployed to GitHub Pages. Here's my info:

- **GitHub username:** YOUR_USERNAME
- **Repo name:** YOUR_REPO (already created on GitHub)
- **Site title:** YOUR_SITE_TITLE
- **Author name:** YOUR_NAME
- **Author bio:** A SHORT BIO
- **Location:** YOUR_LOCATION (optional)

Do the following steps in order:

### 1. Initialize the Hugo site

```
hugo new site . --force
```

### 2. Add the Weaver theme as a git submodule

```
git submodule add https://github.com/highb/weaver.git themes/weaver
```

### 3. Configure `hugo.toml`

Set it up with these values:

```toml
baseURL = "https://YOUR_USERNAME.github.io/YOUR_REPO"
languageCode = "en-us"
title = "YOUR_SITE_TITLE"
theme = "weaver"

[params]
  defaultTheme = ""

  [params.author]
    name = "YOUR_NAME"
    bio = "YOUR_BIO"
    url = "https://YOUR_USERNAME.github.io/YOUR_REPO"

[menu]
  [[menu.main]]
    name = "Home"
    url = "/"
    weight = 1

  [[menu.main]]
    name = "Posts"
    url = "/posts/"
    weight = 2

  [[menu.main]]
    name = "About"
    url = "/about/"
    weight = 3
```

Add any social links you want under `[[params.social]]` with `name` and `url` fields.

### 4. Create a `.gitignore`

```
public/
resources/_gen/
.hugo_build.lock
.DS_Store
Thumbs.db
```

### 5. Create an about page at `content/about.md`

Write a short about page with my info. Set `draft = false`.

### 6. Create a first blog post at `content/posts/`

Pick any topic I've mentioned or write a short intro post. Set `draft = false` and today's date.

### 7. Set up GitHub Pages deployment

Create `.github/workflows/hugo.yml` with a workflow that:
- Triggers on push to `main`
- Installs Hugo extended
- Checks out the repo with submodules
- Builds with `hugo --gc --minify`
- Deploys to GitHub Pages using `actions/deploy-pages@v4`

Then enable GitHub Pages on the repo to use GitHub Actions as the build source:

```
gh api repos/YOUR_USERNAME/YOUR_REPO/pages -X PUT -f build_type=workflow -f source.branch=main -f source.path="/"
```

### 8. Commit and push

Commit everything and push to `origin main`.

### 9. Writing new posts

After setup, I can create new posts by asking:

> Write a new blog post about TOPIC

Posts go in `content/posts/` as markdown files with this front matter:

```
+++
date = 'YYYY-MM-DD'
draft = false
title = 'Post Title'
+++
```

To preview locally before pushing: `hugo server -D`

---

That's it. After the push, the site will be live at `https://YOUR_USERNAME.github.io/YOUR_REPO/` once the Actions workflow completes.
