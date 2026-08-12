# blog

A simple static blog — plain HTML and CSS, no build step — designed to be hosted for free on GitHub Pages.

## Structure

```
index.html            Home page — intro, plus the playbook board
writing.html          The list of posts, grouped by month
style.css             Site styles (light + dark mode)
sam-photo.jpg         Author photo, used on the home and writing pages
hello-world.html      A blog post — every post lives at the root
.nojekyll             Tells GitHub Pages to serve files as-is
```

The home page pairs a short pitch on the left with the playbook board on the
right, sized so the whole board lands above the fold, and a note about the
playbook further down. The name sits above the board's own title, so it travels
with a screenshot of it. It is one self-contained file: the layout data, the hand-drawn SVG helpers and the icons
all live in the `<script>` at the bottom of `index.html`, in plain JavaScript
with no framework and no build step. To change the board, edit the `STEPS`,
`DAYS` and `ADVANCED` arrays at the top of that script — `x`/`y` are coordinates
in a fixed 1470×1300 world that is scaled down to fit the room it is given. A
step becomes a clickable yellow button as soon as it is given a `url`.

Beside the photo the board is fitted to the viewport height as well as the
width; stacked underneath it on a narrow screen, only the width counts. Either
way it stops shrinking at `MIN_K_BESIDE` / `MIN_K_STACKED`, where the lettering
gives out, and the card scrolls sideways instead.

Posts are not nested in a subfolder: each one sits at the root and is served at
`/<post-name>.html`. Links between posts should be relative (`weekly-sprint-playbook.html`),
not root-absolute (`/weekly-sprint-playbook.html`), so they also work when previewing
files locally.

## Viewing locally

Just open `index.html` in a browser, or run a tiny local server:

```sh
python3 -m http.server
```

Then visit http://localhost:8000.

## Publishing to GitHub Pages

1. Push this repo to GitHub.
2. Go to **Settings → Pages**.
3. Under **Build and deployment**, set **Source** to **Deploy from a branch**.
4. Choose the `main` branch and the `/ (root)` folder, then **Save**.
5. After a minute your site will be live at `https://<username>.github.io/<repo>/`.

## Adding a new post

1. Copy `hello-world.html` and rename it (e.g. `my-post.html`).
2. Edit the title, date, and content.
3. Add a link to it from the post list in `writing.html`.
4. If the post belongs to a step on the playbook, set that step's `url` in `index.html`.
