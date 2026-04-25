# My Blog

This repository is configured as a GitHub Pages blog using the [Just the Docs](https://github.com/just-the-docs/just-the-docs) Jekyll theme.

## Local preview

Install Ruby and Bundler, then run:

```bash
bundle install
bundle exec jekyll serve
```

## GitHub Pages

In the GitHub repository settings, go to **Pages** and set **Build and deployment** to **GitHub Actions**.

The workflow in `.github/workflows/pages.yml` builds and deploys the site from the `main` branch.
