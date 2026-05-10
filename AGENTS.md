# AGENTS.md

## Cursor Cloud specific instructions

This is a static HTML/CSS portfolio site with no backend, database, or JavaScript. There are no automated tests.

### Running the dev server

```bash
serve -l 5503 /workspace
```

The site is then available at `http://localhost:5503/`.

### SCSS compilation

The stylesheets use SCSS (Sass). The entry point is `assets/styles/_combined.scss` which imports 7 partials. The compiled output `assets/styles/combined.css` is committed in compressed form.

To recompile after editing `.scss` files:

```bash
sass --style=compressed assets/styles/_combined.scss assets/styles/combined.css
```

### Key notes

- No `package.json`, no `node_modules`, no lockfile — dependencies are installed globally (`serve`, `sass`).
- The `.vscode/settings.json` configures VS Code Live Server on port 5503; `serve` replicates this for headless environments.
- No lint or test commands exist. SCSS compilation (`sass`) serves as the build/validation step.
- Opening `index.html` via `file://` may cause SVG filters and font loading issues; always use a local HTTP server.
