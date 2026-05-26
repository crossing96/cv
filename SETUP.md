# Your online CV (sharu725/online-cv)

This repo is based on [online-cv](https://github.com/sharu725/online-cv). Almost all resume content lives in **`_data/data.yml`**.

## Edit your CV

1. Open **`_data/data.yml`** and replace placeholders (name, experience, skills, links).
2. Put a square profile photo at **`assets/images/profile.png`** (about 100×100 px).
3. Optional: change color in **`_config.yml`** → `theme_skin` (blue, teal, green, berry, orange, ceramic, …).

Optional sections (add blocks to `data.yml` when you need them):

- `certifications`
- `projects`
- `oss`
- `publications`
- `recommendations`

See the [upstream example](https://github.com/sharu725/online-cv/blob/master/_data/data.yml) for full YAML shapes.

## Preview locally

### Option A — Docker (easiest on Windows)

```powershell
cd C:\Users\PC\Documents\GitHub\cv
docker-compose up
```

Open http://localhost:4000

### Option B — Ruby + Jekyll

```powershell
cd C:\Users\PC\Documents\GitHub\cv
bundle install
bundle exec jekyll serve
```

Open http://localhost:4000

For local preview, `_config.yml` uses `url: 'http://localhost:4000'`. Change `url` before deploying.

## PDF

- On the site: use the **Print** or **PDF** button, or open **`/print`** (e.g. `https://yoursite.com/print`).
- Browser print → Save as PDF works well.

## Deploy to your domain (jongyeobkim.com)

This CV repo uses its **own** custom domain, separate from `pubxel.org` on `crossing96.github.io`.

1. Push **`CNAME`** (`jongyeobkim.com`) and **`_config.yml`** (`url` + empty `baseurl`).
2. GitHub **crossing96/cv** → **Settings → Pages → Custom domain** → `jongyeobkim.com` → Save → enable **Enforce HTTPS**.
3. At your **jongyeobkim.com** DNS host, add the records GitHub shows (typically **A** records for apex, **CNAME** for `www` if used).
4. Wait for DNS check to pass (minutes to 48h).

**Note:** `https://pubxel.org/cv` may still work because GitHub mirrors project repos under your user-site custom domain. Use **https://jongyeobkim.com** as the public link for your CV.

### Other hosts

Run `bundle exec jekyll build`, upload the **`_site`** folder to Netlify, Cloudflare Pages, or your server.

## Git remote

After cloning, point `origin` at your own repo:

```powershell
git remote set-url origin https://github.com/YOUR_USER/cv.git
```

## Cursor workflow

- Edit `_data/data.yml` and `_config.yml`.
- Run `docker-compose up` or `bundle exec jekyll serve` in the integrated terminal.
- Refresh the browser to see changes (Docker uses live reload).
