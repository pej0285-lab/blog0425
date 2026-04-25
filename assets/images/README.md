# Images

Use this directory for blog images.

## Recommended structure

Store post images in a folder named after the post date and slug:

```text
assets/images/posts/2026-04-25-github-pages/
```

Example:

```text
assets/images/posts/2026-04-25-github-pages/settings-pages.png
```

Use the image in a post like this:

{% raw %}
```markdown
![GitHub Pages settings]({{ "/assets/images/posts/2026-04-25-github-pages/settings-pages.png" | relative_url }})
```
{% endraw %}

## Site images

Use `assets/images/site/` for shared images such as logos, favicons, and screenshots used across multiple pages.
