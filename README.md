# Linked Objects — Demo Pod

A handful of [linked-object](https://linkedobjects.org) resources hosted as static files on GitHub Pages, each rendered by the [Linked Object Browser](https://linkedobjects.org/browser/).

Live: <https://linkedobjects.org/demo/>

## What's here

| Path | Type | What you see |
|------|------|--------------|
| `/profile/` | `foaf:Person` | A profile pane |
| `/tasks/` | `wf:Tracker` | A to-do list (Tasks pane) |
| `/notes/` | `TextDocument` (`text/markdown`) | Rendered markdown |
| `/playlist/` | `Playlist` (`audio/mpegurl`) | Audio queue (Playlist pane) |
| `/folder/` | `ldp:BasicContainer` | Directory listing |

## How it works

Each URL is a static HTML file containing two things:

```html
<div id="mashlib"></div>

<script type="application/ld+json">
  { "@id": "#this", "@type": "...", ... }
</script>

<script type="module" src="https://linkedobjects.org/browser/mashlib.js"></script>
```

The browser finds the data island, picks the matching pane, and renders. No backend, no JSS, no build step — just inline JSON-LD and the mashlib module.

To change a resource, edit its `index.html`, push to `gh-pages`, reload.

## License

[AGPL-3.0](https://github.com/linkedobjects/browser/blob/gh-pages/LICENSE) — same as the browser.
