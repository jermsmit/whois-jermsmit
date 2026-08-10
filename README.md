# whois.jermsmit.com

A single-page personal identity site. Static HTML, CSS, and a small amount of
vanilla JavaScript. No build step, no framework, no CMS.

## File structure

```
index.html        the whole page
css/styles.css     all styling
js/main.js         mobile menu toggle + footer year
assets/profile.jpg your headshot
```

## Publishing with GitHub Pages

1. Create a new GitHub repository, for example `whois-jermsmit`.
2. Push these files to the `main` branch (root of the repo, not a subfolder).
3. In the repo, go to **Settings > Pages**.
4. Under **Build and deployment**, set Source to **Deploy from a branch**,
   branch `main`, folder `/ (root)`. Save.
5. GitHub will give you a URL like `https://jermsmit.github.io/whois-jermsmit`.
   That confirms the deploy is working.
6. To use `whois.jermsmit.com`: in your DNS provider, add a `CNAME` record
   for the `whois` subdomain pointing to `jermsmit.github.io`. Then in the
   repo's **Settings > Pages > Custom domain**, enter `whois.jermsmit.com`
   and save. Check "Enforce HTTPS" once the certificate is issued (can take
   up to 24 hours).

## Making content changes later

Everything is in plain HTML, so edits are direct:

- **Text**: open `index.html`, find the section (marked with an HTML
  comment like `<!-- PROJECTS -->`), and edit the text between the tags.
- **Colors and fonts**: open `css/styles.css`, edit the values at the top
  under `:root`. Everything else on the page references those values, so a
  single change there updates the whole site.
- **New project card**: copy one `<article class="project-card">` block in
  the Projects section and edit its contents.
- **New log entry**: copy one `<div class="log-entry">` block in the Track
  Record section and edit its contents.

## Workflow for changes (branches and PRs, in simple terms)

You do not need to work directly on `main` if you want a safety net:

1. Create a new branch for the change, e.g. `update-projects`.
2. Edit the file(s) on that branch and commit.
3. Open a Pull Request comparing `update-projects` into `main`.
4. Review the diff on GitHub (it shows exactly what changed), then click
   **Merge**.
5. GitHub Pages redeploys automatically a few seconds after the merge.

For small text tweaks, editing directly on `main` through GitHub's web
editor is fine too. The branch/PR flow is mainly useful if you want to
preview a bigger change before it goes live.

## Notes

- No email address or phone number appears anywhere on the site by design.
  LinkedIn is the single point of contact.
- All external links (LinkedIn, GitHub, Substack, blog, Our Beautiful
  Foundation) open in a new tab.
- The site respects `prefers-reduced-motion` and includes visible keyboard
  focus states for accessibility.
