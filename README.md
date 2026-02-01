# Weaver Demo

A demo blog built with [Hugo](https://gohugo.io/) and the [Weaver](https://github.com/highb/weaver) theme, an IndieWeb-friendly theme for personal websites.

This entire site — content, configuration, and deployment — was generated through conversation using [Claude Code](https://claude.com/claude-code) and Claude Sonnet 4.5.

**Live site:** https://highb.github.io/weaver-demo

## What's in here

- Two blog posts about the web's origins and the emerging indie LLM web
- An about page
- GitHub Actions workflow for automatic deployment to GitHub Pages
- The Weaver theme as a git submodule

## Build your own

You can create a site like this one by having a conversation with an AI coding assistant. You describe what you want in plain language, and it writes the code and runs the commands for you. No prior experience with web development is required.

Here's what you'll need to do, starting from scratch.

### Step 1: Create a GitHub account

[GitHub](https://github.com/) is a free platform that stores your website's code and can host it for free. You'll need an account.

1. Go to [github.com/signup](https://github.com/signup) and create a free account
2. Once signed in, create a new repository (the "+" button in the top right, then "New repository"). Give it a name like `my-blog`. Check "Public" and click "Create repository"
3. Keep this browser tab open — you'll need the repository name later

### Step 2: Set up an AI coding tool

An **agentic coding tool** is an AI assistant that can write code, create files, and run commands on your computer through conversation. You tell it what you want, and it does the work. Think of it like a knowledgeable friend sitting next to you at the keyboard.

There are several options. Here are a few that work well for this kind of task:

- **[Claude Code](https://docs.anthropic.com/en/docs/claude-code)** — Anthropic's command-line coding tool. This is what built this site. It requires a terminal (see Step 3) and an [Anthropic API account](https://console.anthropic.com/) or a [Claude Max subscription](https://claude.ai). Install it by typing `npm install -g @anthropic-ai/claude-code` in your terminal after installing Node.js.
- **[Claude.ai](https://claude.ai)** — If you'd rather stay in the browser, you can use Claude's web interface. It can't run commands directly on your computer, but it can generate all the files and give you step-by-step instructions to run the commands yourself.

Pick whichever you're most comfortable with. If you're not sure, Claude.ai in the browser is the easiest starting point — you can always move to Claude Code later.

### Step 3: Get a terminal (if using Claude Code)

A **terminal** (also called a command line) is a text-based interface for running commands on your computer. If you're using Claude Code, you'll need one.

- **Mac:** Open the built-in app called "Terminal" (search for it in Spotlight with Cmd+Space)
- **Windows:** Install [Windows Terminal](https://aka.ms/terminal) from the Microsoft Store, then install [WSL](https://learn.microsoft.com/en-us/windows/wsl/install) (Windows Subsystem for Linux) by opening Terminal and running `wsl --install`
- **Linux:** You already have one
- **Chromebook:** Enable [Linux on ChromeOS](https://support.google.com/chromebook/answer/9145439) in Settings

You'll also need to install a few things through the terminal:
- **[Git](https://git-scm.com/downloads)** — for tracking changes and pushing to GitHub
- **[Node.js](https://nodejs.org/)** — needed to install Claude Code (download the LTS version)
- **[Hugo](https://gohugo.io/installation/)** — the tool that builds your site
- **[GitHub CLI](https://cli.github.com/)** — for connecting to GitHub from the terminal (run `gh auth login` after installing)

If any of this feels overwhelming, paste these instructions into Claude.ai and ask it to walk you through the installation for your specific computer. That's a perfectly valid way to do it.

### Step 4: Build your site

Once you have a coding tool set up, open [PROMPT.md](PROMPT.md) and follow the instructions there. It contains a ready-to-paste prompt — fill in your details (name, GitHub username, etc.) and give it to your AI coding tool. It will set up everything and deploy your site.

### Step 5: Start writing

After setup, creating new content is as simple as telling your AI tool:

> Write a new blog post about \[topic\]

Then commit and push to publish it.

## Learning more

New to all of this? [LEARN.md](LEARN.md) explains every technology the site uses, from the ground up, with links to free learning resources. There's no pressure to understand it all — or any of it. You can go as deep as you want.

## Local development

If you have Hugo installed, you can preview your site before publishing:

```
hugo server -D
```

This starts a local server — open the URL it prints in your browser to see your site.
