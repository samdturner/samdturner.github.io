# blog

A simple static blog — plain HTML and CSS, no build step — designed to be hosted for free on GitHub Pages.

## Structure

```
index.html            Home page with the list of posts
style.css             Site styles (light + dark mode)
blog/
  hello-world.html    A blog post
.nojekyll             Tells GitHub Pages to serve files as-is
```

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

1. Copy `blog/hello-world.html` and rename it (e.g. `blog/my-post.html`).
2. Edit the title, date, and content.
3. Add a link to it from the post list in `index.html`.
