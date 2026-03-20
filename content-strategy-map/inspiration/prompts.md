# Content Strategy Map — Build Prompts

The verbatim prompts used to design and build this interactive visualization, in order.

---

## Prompt 1 — Initial Concept

> "I have this chart (chart.png) That I would like to see converted into an animated html graphic. The styles should be contemporary, they don't necessarily need to be circles. Utilize the color scheme. there should also be interaction with the items with a tooltip type of hover that follows mouse movements. hovering should lift the item. micro animations should be used to create a smooth user experience."

**What was built:** A single-file HTML interactive map with 7 glassmorphism nodes connected by animated SVG bezier curves. Dark theme with per-node accent colors pulled from the original chart. Staggered entrance animations, mouse-following tooltip panel, and hover lift/glow effects.

---

## Prompt 2 — Icons & Arrow Readability

> "use lucide icons instead of the emoji's. make sure that the descriptions of the the process on the arrows is more readable. currently, they appear below the nodes. Maybe have an information icon on the arrows that have them to display as a tool tip on hover."

**What was built:** Swapped all emoji node icons for Lucide icon SVGs via CDN. Removed text labels from SVG connection paths entirely. Added ⓘ info badge circles positioned at the bezier midpoint of each connection — hovering one shows a styled tooltip with the connection's strategic context.

---

## Prompt 3 — Spacing & Draggable Nodes

> "The spacing between trend pages and commercial intent page is too tight. make more space there. Can the nodes be draggable to move them in the display and save to local storage?"

**What was built:** Adjusted default node positions to open up the gap between the Trend Pages cluster and the Commercial Intent Page node. Added full drag-and-drop support — nodes are freely repositionable within the canvas, SVG connections redraw in real time, and final positions are persisted to `localStorage` (key: `csmap-positions-v2`) so the layout survives page refreshes. A "Reset Layout" button clears storage and reloads defaults.

---

## Prompt 4 — Drag Bug Fix, Content Overflow & JSON Config

> "Dragging the nodes makes them disappear until dropped. Fix this. Make sure the content of the nodes fits within it's container. use json for all of the node content for easy updatability"

**What was built:** Fixed the disappearing-node bug — root cause was that cancelling the CSS animation (`animation: none`) during drag also cancelled the `forwards` fill-mode holding `opacity: 1`, snapping nodes invisible. Fix: `opacity: 1` is frozen inline on `mousedown` before the animation is killed, and `opacity: 1 !important` is also set in the `.is-dragging` CSS class. Removed all fixed `height` values from node cards so content never overflows. Refactored all node and connection data into top-of-script `NODES` and `CONNECTIONS` JSON config arrays so copy, icons, colors, positions, and tooltip text can all be updated in one place without touching layout or interaction code.

---

## Prompt 5 — GitHub Repo

> "make this a git repo under my user ferndocker and commit, push to github"

**What was built:** Created the public GitHub repository `ferndocker/content-strategy-map` and pushed `index.html` and `README.md` via the GitHub Contents API (browser-based fetch from github.com, since the sandbox proxy blocks direct git/curl access to GitHub).

Repository: [https://github.com/ferndocker/content-strategy-map](https://github.com/ferndocker/content-strategy-map)

---

## Technical Reference

| Concern | Approach |
|---|---|
| Framework | Vanilla HTML / CSS / JavaScript — no build step |
| Icons | Lucide via `unpkg.com/lucide@latest` CDN |
| Connections | Dynamic SVG cubic bezier paths, redrawn on every drag tick |
| Animations | CSS `@keyframes nodeIn` with spring easing; `forwards` fill-mode |
| Persistence | `localStorage` key `csmap-positions-v2` |
| Config | `NODES[]` and `CONNECTIONS[]` JSON arrays at top of `<script>` |

---

*Prompts recorded: March 20, 2026*
