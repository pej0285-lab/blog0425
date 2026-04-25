---
title: Getting Started
layout: default
nav_order: 3
---

# Getting Started

This page is a small reference for maintaining the site.

## Local preview

```bash
bundle install
bundle exec jekyll serve
```

The local preview usually runs at `http://localhost:4000`.

## Publishing

Push changes to the `main` branch. The included GitHub Actions workflow builds the site and deploys it to GitHub Pages.
