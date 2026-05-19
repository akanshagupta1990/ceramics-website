# Ceramics — Akansha Gupta

A minimal portfolio site for Spring & Winter 2026 ceramic work.

## Local preview

Open `index.html` in a browser, or run:

```bash
python3 -m http.server 8000
```

Then visit [http://localhost:8000](http://localhost:8000).

## Deploy to GitHub Pages

### 1. Accept the Xcode license (if `git` fails)

```bash
sudo xcodebuild -license
```

### 2. Create the repo and push

From this folder:

```bash
cd "/Users/akanshagupta/Projects/Ceramics website"

git init
git add .
git commit -m "Initial commit: ceramics portfolio site"

gh repo create ceramics-website --public --source=. --remote=origin --push
```

Use a different repo name if you prefer; change `ceramics-website` above.

If you don’t use GitHub CLI, create an empty repo at [github.com/new](https://github.com/new), then:

```bash
git remote add origin https://github.com/YOUR_USERNAME/ceramics-website.git
git branch -M main
git push -u origin main
```

### 3. Turn on GitHub Pages

```bash
gh api repos/{owner}/ceramics-website/pages -X POST \
  -f build_type=legacy \
  -f source[branch]=main \
  -f source[path]=/
```

Or in the browser: **Repo → Settings → Pages → Build from branch `main` / root (`/`)**.

Your site will be live at:

**https://YOUR_USERNAME.github.io/ceramics-website/**

(First deploy can take 1–2 minutes.)

## Updating the site

After changing photos or `products.js`:

```bash
git add .
git commit -m "Update gallery"
git push
```

GitHub Pages will rebuild automatically.
