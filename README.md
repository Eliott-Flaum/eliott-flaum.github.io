# Eliott Flaum — Personal Site

A simple static, multi-page site — no build step, no dependencies, just plain files:

- `index.html` — About (home page, includes a condensed Research section)
- `publications.html` — Publications
- `experience.html` — Experience
- `contact.html` — Contact
- `style.css` — shared styling for all pages
- `fig-lacrymaria-cytoskeleton.jpg`, `fig-diatom-expansion-microscopy.jpg`, `fig-marine-snow-flagellate.jpg` — figures shown next to their respective papers on the Publications page
- `script.js` — small script that fills in the footer year

## 1. Edit your content

Open any page in Sublime Text (or your editor of choice). Every spot you should personalize is marked with an HTML comment like `<!-- edit: ... -->` or bracketed text like `[your field]`. Replace those with your real details — see each file for its relevant section.

Each page repeats the same header (name, role, nav) and footer, so if you want to change your name or role, update it in all five files, or use Sublime's Find & Replace across the folder (Find → Find in Files).

Preview by double-clicking any `.html` file to open it in your browser — no server needed. Since it's a real multi-page site now, clicking the nav links will actually navigate between separate pages.

## 2. Put it on GitHub

### Step A: Rename your GitHub username to `eliott-flaum`

1. Log into GitHub, go to **Settings** (click your profile photo → Settings).
2. On the **Account** tab (bottom of the general settings page), find **Change username**.
3. Enter `eliott-flaum` and confirm. GitHub will check it's available and warn you about the rename (old repo URLs and profile links redirect automatically, so nothing breaks).

### Step B: Create the repository

1. Create a new repository named **exactly** `eliott-flaum.github.io` — this exact match is what makes GitHub serve it as your personal site. Choose **Private** for now if you're not ready to launch — you can flip it to Public later (note: GitHub Pages on a free plan only serves *public* repos, so the live site won't be reachable until you make it public).
2. Upload all files (`index.html`, `publications.html`, `experience.html`, `contact.html`, `style.css`, `script.js`, and your photo) to the repository, either by dragging them into the GitHub web UI or via git:
   ```bash
   git init
   git add .
   git commit -m "Initial site"
   git branch -M main
   git remote add origin https://github.com/eliott-flaum/eliott-flaum.github.io.git
   git push -u origin main
   ```
3. In the repo, go to **Settings → Pages**, and under "Source" choose the `main` branch and `/ (root)` folder, then save.
4. Once the repo is public, your site will be live at **https://eliott-flaum.github.io**, with each page reachable via its own URL (e.g. `https://eliott-flaum.github.io/publications.html`).

## 3. Custom domain (optional)

If you own a domain (e.g. `eliottflaum.com`) and want to use it instead:

1. In the same repo, go to **Settings → Pages → Custom domain**, enter your domain, and save (this creates a `CNAME` file automatically).
2. At your domain registrar, add these DNS records:
   - Four `A` records for the apex domain pointing to GitHub's IPs: `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`
   - A `CNAME` record for `www` pointing to `<your-username>.github.io`
3. DNS changes can take up to 24 hours to propagate.

## Notes

- Fonts (Newsreader, Inter) load from Google Fonts via the `<link>` tags in `index.html`.
- The design uses no external frameworks, so it stays fast and easy to hand-edit.
