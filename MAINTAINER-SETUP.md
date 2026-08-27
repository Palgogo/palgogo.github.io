# Setup and Resources

Maintainer-only reference for local setup and official documentation.
This file is intentionally outside `docs/` so it is not published to GitHub Pages.

## Quick setup

```bash
python3 -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
mkdocs serve
```

Useful commands:

- `mkdocs serve` - run local dev server with live reload
- `mkdocs build --strict` - build site and fail on warnings/errors

## MkDocs documentation

- [MkDocs official documentation](https://www.mkdocs.org/)
- [MkDocs user guide](https://www.mkdocs.org/user-guide/)
- [MkDocs configuration reference](https://www.mkdocs.org/user-guide/configuration/)
- [MkDocs deployment guide](https://www.mkdocs.org/user-guide/deploying-your-docs/)

## Theme resources

- [Material for MkDocs documentation](https://squidfunk.github.io/mkdocs-material/)
- [Material for MkDocs getting started](https://squidfunk.github.io/mkdocs-material/getting-started/)
- [Material for MkDocs setup guide](https://squidfunk.github.io/mkdocs-material/setup/)
- [MkDocs themes catalog](https://github.com/mkdocs/catalog?tab=readme-ov-file#-themes)

## Notes for this site

- Current theme: Material for MkDocs
- Current deploy model: GitHub Actions + Pages artifact deployment
- Canonical public URL: `https://blog.palgogo.com/`; `https://palgogo.com/` redirects there.
- Custom domain: the repository-root `CNAME` must contain exactly `blog.palgogo.com`. The deployment workflow copies it into the Pages artifact after MkDocs builds.
- In GitHub Settings → Pages, keep the custom domain set to `blog.palgogo.com` and enable **Enforce HTTPS** only after GitHub has issued its certificate.
- In Cloudflare DNS, the `blog` CNAME target is `palgogo.github.io` and must remain **DNS only** while GitHub Pages validates and renews its certificate. Verify after changes with `curl -Iv https://blog.palgogo.com/`.
