# Noodle Map

A dark, node-based mind map editor inspired by Blender's geometry nodes. Thoughts are nodes with a title, a color and an optional note; links between them are curved "noodles" that fade from one thought's color into the other's.

It's a single HTML file with no build step and no dependencies. Open `index.html` in a browser, or serve the repository with GitHub Pages.

## Features

- **Thoughts as nodes**: title, color (9 presets or any custom color), note, collapse
- **Connect any socket to any socket**: Out→In, Out→Out, In→In; sockets stretch when several links share them
- **Groups**: select thoughts and press `Ctrl G` to frame them with a name and color
- **Save as**: `.json` (re-importable), `.png`, `.svg`, or a `.md` outline
- **Import**: `.json` maps or any Markdown outline (headings and bullet lists), by button, drag-and-drop or paste
- **Autosave** in the browser, plus undo/redo
- **Tidy layout**, frame all, zoom, pan, touch and pinch support

## Shortcuts

| Keys | Action |
| --- | --- |
| Double-click canvas | New thought |
| `Shift A` | Add menu |
| Drag a socket | Connect (release on empty space to add a connected thought) |
| `Alt` + drag socket | Pull a link off |
| `Ctrl` + right-drag | Cut links |
| `Ctrl G` / `Ctrl Shift G` | Group / ungroup |
| `Alt P` | Remove from group |
| `F2` / double-click title | Rename |
| `X` / `Delete` | Delete |
| `Ctrl D` | Duplicate |
| `H` | Collapse |
| `A` / `Alt A` | Select all / none |
| `Home` / `F` | Frame all / frame selected |
| `Ctrl Z` / `Ctrl Shift Z` | Undo / redo |
| `Ctrl S` / `Ctrl O` | Save as / import |
| `N` | Toggle sidebar |
| Scroll | Zoom |
| Middle or right drag, `Space` + drag | Pan |

## File format

Saved `.json` maps look like this:

```json
{
  "app": "noodle-map",
  "version": 1,
  "name": "My map",
  "nodes": [{ "id": "a", "x": 0, "y": 0, "title": "Idea", "color": "#d97757", "note": "", "collapsed": false }],
  "links": [{ "id": "l1", "from": "a", "to": "b", "fs": "out", "ts": "in" }],
  "groups": [{ "id": "g1", "title": "Group", "color": "#8a877d", "members": ["a", "b"] }]
}
```
