# privatepayments.org

Private Payments Website

## Development

Install a release build of [Zola](https://github.com/getzola/zola/releases). Serve the development build from the repository root.

```bash
zola serve
```

## Deployment

Build the site with `zola build`. Serve the static site with [Static Web Server](https://sws.joseluisq.net/download-and-install/) from the repository root.

```bash
zola build
static-web-server &
```
