# personal website

Built with [Hugo](https://gohugo.io). Every push to `master` is built and deployed to GitHub Pages by `.github/workflows/hugo.yml`.

## Run locally

```
hugo server        # http://localhost:1313, reloads on save
hugo server -D     # also show drafts
```

## Where things are

- Homepage bio and links: `content/_index.md`
- Publications (full list at /publications/; `selected: true` puts one on the homepage): `data/publications.yaml`
- Talks (homepage shows the three newest): `data/talks.yaml`
- Blog posts: `content/blogs/*.md`. Start a new one with `hugo new content blogs/my-post.md` (it begins as a draft; delete `draft: true` to publish).
- Standalone HTML pages (served as-is): `static/`
- Styles: `assets/css/main.css`. Templates: `layouts/`
