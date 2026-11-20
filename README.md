# Leonardo da Vinci · Mona Lisa

Leonardo da Vinci's the Portrait of Lisa Gherardini (Louvre, INV 779) — a narrated deep-zoom tour (in English), as a static page.

The painting at full resolution beside callouts on its details — the crack, the eyebrows, the smile, the winding road, the bridge, the unfinished ground, the hands — and three panels: who she was, the 1911 theft, and what lies under the varnish.

Live: https://youdata.github.io/leonardo-mona-lisa/

The image pyramid is a tile folder (`monalisa/`: `header.idx` + `{z}/{x}/{y}.png`), so any static host serves it. Its fonts
are in `fonts/`, trimmed to the page's characters. The narrated video is not included.

## How it is made

From `infographic-examples/leonardo-mona-lisa/build.mjs` (the page; its facts and quotations in `sources.md` there) with rx (`~/rx-cli`):

```sh
node build.mjs                                                     # → leonardo-mona-lisa.json
rx export leonardo-mona-lisa.json --out site --app /rx-graphic-editor/web/index.html --canvas --theme dark --lock-layers --tiles dir
rx publish site --to github:youdata/leonardo-mona-lisa --yes
```
