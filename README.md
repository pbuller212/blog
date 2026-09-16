# blog

Personal/technical blog built with [Hugo](https://gohugo.io/) and the
[PaperMod](https://github.com/adityatelange/hugo-PaperMod) theme, deployed to
[GitHub Pages](https://pbuller212.github.io/blog/) via GitHub Actions.

This repo lives primarily on a self-hosted Forgejo instance and is mirrored
to GitHub (`pbuller212/blog`) so GitHub Actions can build and deploy it to
Pages on every push to `main`.

## Local development

Clone with submodules (the theme is a git submodule):

```sh
git clone --recurse-submodules <repo-url>
cd blog
```

If you already cloned without `--recurse-submodules`:

```sh
git submodule update --init --recursive
```

Run the local dev server with drafts enabled:

```sh
hugo server -D
```

Build the site (output goes to `public/`, which is gitignored and never
committed):

```sh
hugo build
```

## Adding a new post

```sh
hugo new content posts/my-post-title.md
```

Edit the new file under `content/posts/`, set `draft = false` when ready to
publish, and push to `main`. The GitHub Actions workflow
(`.github/workflows/hugo.yaml`) builds and deploys automatically.
