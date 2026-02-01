+++
date = '2026-02-01'
draft = false
title = 'Learning Guide'
+++

If you used the [Build Your Own](/prompt/) prompt to set up your site, a lot just happened very quickly. You now have a working website, but you might not understand how or why it works. That's completely okay. You don't need to understand everything at once — or ever, honestly. Plenty of people drive cars without knowing how engines work.

But if you're curious, this guide walks through the technologies your site uses, starting from the basics. Take it at your own pace.

## The Web: HTML, CSS, and Browsers

Everything on the web boils down to a few simple ideas. When you visit a website, your browser (Chrome, Firefox, Safari, etc.) downloads files from a server and displays them. The most important file types are:

- **HTML** — the structure and content of a page (headings, paragraphs, links, images)
- **CSS** — the visual styling (colors, fonts, layout, spacing)

Your Hugo site generates these files for you. You write in Markdown (see below), and Hugo converts it into HTML and CSS that browsers understand.

**Learn more:**
- [MDN: Getting started with the web](https://developer.mozilla.org/en-US/docs/Learn/Getting_started_with_the_web) — Mozilla's free, beginner-friendly introduction
- [Interneting Is Hard](https://internetingishard.netlify.app/) — a friendly guide to HTML and CSS

## Markdown: Writing Without Code

You don't write HTML directly. Instead, you write in **Markdown**, a simple formatting language. For example:

```markdown
# This is a heading

This is a paragraph with **bold** and *italic* text.

- This is a list item
- So is this

[This is a link](https://example.com)
```

Your blog posts and about page are all Markdown files. That's all you need to edit to update your site's content.

**Learn more:**
- [Markdown Guide](https://www.markdownguide.org/getting-started/) — a clear, practical introduction
- [CommonMark tutorial](https://commonmark.org/help/tutorial/) — an interactive 10-minute tutorial

## Hugo: Turning Markdown into a Website

[Hugo](https://gohugo.io/) is a **static site generator**. It takes your Markdown files and a theme (Weaver, in your case) and produces a folder of HTML and CSS files — a complete website ready to be served.

Key concepts:
- **`content/`** — where your writing lives (posts, pages)
- **`hugo.toml`** — your site's configuration (title, author info, menus)
- **`themes/`** — the template and styling for your site
- **`public/`** — the generated site (you don't edit this; Hugo builds it)

To preview your site locally, run `hugo server -D` and open the URL it gives you in your browser. Changes you make to files will appear immediately.

**Learn more:**
- [Hugo quick start](https://gohugo.io/getting-started/quick-start/)
- [Hugo content organization](https://gohugo.io/content-management/organization/)

## Git: Tracking Changes

[Git](https://git-scm.com/) is a version control system. It keeps a history of every change you make to your files, so you can always go back to a previous version if something breaks. Think of it like infinite undo for your entire project.

Key commands you'll use:
- `git add <file>` — stage a file to be saved
- `git commit -m "description"` — save a snapshot with a message
- `git push` — send your changes to GitHub

You don't need to memorize these. Your LLM coding tool handles them for you. But it's helpful to know what's happening.

**Learn more:**
- [Git basics (GitHub guide)](https://docs.github.com/en/get-started/getting-started-with-git)
- [Oh My Git!](https://ohmygit.org/) — a game for learning git

## GitHub: Hosting Your Code

[GitHub](https://github.com/) is a platform that stores your git repositories (project folders) online. It also provides **GitHub Pages**, a free hosting service that serves your site to the world.

When you push changes with git, GitHub receives them, runs a build process (see below), and publishes your updated site automatically.

**Learn more:**
- [GitHub Hello World](https://docs.github.com/en/get-started/start-your-journey/hello-world)
- [GitHub Pages documentation](https://docs.github.com/en/pages)

## GitHub Actions: Automatic Deployment

The file at `.github/workflows/hugo.yml` is a **workflow** — a set of instructions that GitHub runs automatically every time you push changes. Your workflow:

1. Installs Hugo
2. Builds your site from Markdown into HTML
3. Deploys the result to GitHub Pages

You don't need to touch this file. It just works in the background. But if you're curious about what it does, open it up and read the step names — they're fairly self-explanatory.

**Learn more:**
- [Understanding GitHub Actions](https://docs.github.com/en/actions/about-github-actions/understanding-github-actions)

## Git Submodules: The Theme

The Weaver theme lives in `themes/weaver/` as a **git submodule** — essentially a link to another git repository inside yours. This means you get theme updates without copying files around. It also means the theme's code stays separate from your content.

You probably won't need to think about submodules. If something goes wrong with the theme, ask your LLM tool for help.

**Learn more:**
- [Git submodules (Atlassian)](https://www.atlassian.com/git/tutorials/git-submodule)

## The Most Important Thing

The resources above are here if you want them, but the best way to learn is to experiment. Change something in a blog post and see what happens. Edit `hugo.toml` and reload. Break something, then figure out how to fix it (or ask for help fixing it).

You have a safety net: git keeps a history of everything, so you can always get back to a working state. And the site rebuilds automatically, so you'll see results quickly.

When you get stuck:
- Ask your LLM coding tool — it can explain what went wrong and fix it
- More importantly, **ask other people**. Online communities like the [Hugo Discourse forum](https://discourse.gohugo.io/), [IndieWeb chat](https://indieweb.org/discuss), and [freeCodeCamp](https://www.freecodecamp.org/) are full of people who remember what it was like to be new and are happy to help

You don't need permission to learn this stuff, and you don't need to learn it all. Start with what's interesting to you.
