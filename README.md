# blog

A simple static blog — plain HTML and CSS, no build step — designed to be hosted for free on GitHub Pages.

## Structure

```
index.html            Home page with the list of posts
style.css             Site styles (light + dark mode)
sam-photo.jpg         Author photo used on the home page
hello-world.html      A blog post — every post lives at the root
.nojekyll             Tells GitHub Pages to serve files as-is
```

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
3. Add a link to it from the post list in `index.html`.
