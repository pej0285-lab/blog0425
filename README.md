# My Blog

This repository is configured as a GitHub Pages blog using the [Chirpy](https://github.com/cotes2020/jekyll-theme-chirpy) Jekyll theme.

## Local preview

Install Ruby and Bundler, then run:

```bash
bundle install
bundle exec jekyll serve
```

The local preview usually runs at `http://localhost:4000/blog0425/`.

## GitHub Pages

In the GitHub repository settings, go to **Pages** and set **Build and deployment** to **GitHub Actions**.

The workflow in `.github/workflows/pages.yml` builds and deploys the site from the `main` branch.
