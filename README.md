# The Minimal theme

## Previewing the theme locally

If you'd like to preview the theme locally (for example, in the process of proposing a change):

```bash
docker run --rm \
  --volume="$PWD:/srv/jekyll" \
  --publish 127.0.0.1:4000:4000 \
  jekyll/jekyll \
  jekyll serve
```

Visit `localhost:4000` in your browser to preview the theme.
