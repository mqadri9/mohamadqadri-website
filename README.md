# mohamadqadri.com

Static source for Mohamad Qadri's personal academic website.

## Site structure

- `index.html` — homepage
- `stylesheet.css` — homepage styles
- `images/` — publication/profile media used by the homepage
- `data/thesis.html` — Google-Scholar-friendly Ph.D. thesis landing page
- `data/PhD_Thesis_Mohamad_Qadri_Scholar.pdf` — searchable Ph.D. thesis PDF optimized to stay below Google Scholar's 5 MB PDF guideline
- `data/masters_thesis.html` — Master's thesis landing page
- `robots.txt` and `sitemap.xml` — crawl/discovery files

## Push to GitHub

Create an empty GitHub repository, then from this directory:

```bash
git init
git add .
git commit -m "Initial website"
git branch -M main
git remote add origin https://github.com/mqadri9/mohamadqadri-website.git
git push -u origin main
```

If you choose a different repository name, replace the remote URL accordingly.

## Deploy with Cloudflare Pages

In Cloudflare:

1. **Workers & Pages → Create application → Pages → Import an existing Git repository**.
2. Select this repository.
3. Production branch: `main`.
4. Framework preset: none / static HTML.
5. Build command: `exit 0`.
6. Build output directory: `.` (the repository root, where `index.html` lives).
7. Deploy, verify the temporary `*.pages.dev` site, then add `mohamadqadri.com` under **Custom domains**.

After the custom domain is live, keep the old CMU site available during the search/Scholar transition rather than immediately deleting it.

## Google Scholar note

The Ph.D. thesis page deliberately has `citation_*` metadata and a `citation_pdf_url` pointing to a PDF in the same `data/` directory. Keep these two paths stable:

- `https://mohamadqadri.com/data/thesis.html`
- `https://mohamadqadri.com/data/PhD_Thesis_Mohamad_Qadri_Scholar.pdf`

The Master's thesis currently links to the official CMU-hosted PDF; it does not claim a local `citation_pdf_url` because no local Master's PDF is included in this repository.
