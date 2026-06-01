# S4 / DO-Semantics Modality Lattice Explorer

An interactive, single-file explorer for the seven modalities of the modal logic **S4**
and their reading under **Defendant–Opponent (DO) semantics**. Companion to the paper
*Diamonds Are Forever: Stabilization Semantics for Unrestricted Aggregation and Recursion
in Logica*.

The same seven-node Hasse diagram is shown under five interchangeable label sets —
**Modalities**, **DO-Sem** (Figure 1 terms), **DO-Sem′** (suggested renames), **Topology**
(interior/closure), and **CTL** — with the geometry fixed so a node *is* its modality, its
topological operator, and its derivation status at once. Hover a node for every reading;
hover an edge for the implication it encodes, phrased in the currently selected vocabulary.

Live: <https://ludaesch.github.io/s4-do-lattice/>

## Stack

Deliberately minimal: a single self-contained `index.html` with inline CSS and vanilla JS.
No framework, no build step, no dependencies (fonts load from Google Fonts and degrade
gracefully to serif/mono if unavailable).

## Run locally

Just open the file:

```
open index.html        # macOS
xdg-open index.html    # Linux
```

Or serve it (any static server works):

```
python3 -m http.server 8000   # then visit http://localhost:8000/
```

## Deployment

GitHub Pages, "Deploy from a branch":

1. Push this repo to GitHub.
2. Settings → Pages → Source → **Deploy from a branch** → branch `main`, folder `/ (root)`.
3. Live in ~60s at `https://<user>.github.io/<repo>/`.

Because everything is inline in `index.html` at the repo root, there are no asset paths to
rewrite for the `/<repo>/` subpath — no `base:` configuration needed.

## License

MIT.
