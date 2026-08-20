# Unqualified — Fitness Blog

A simple personal fitness blog. Posts are Markdown files in `content/posts/`,
built into pages by Eleventy, and edited through a "New Post / Edit / Delete"
admin panel (Decap CMS) at `/admin` — no database, no code required day-to-day.

## One-time setup (about 15–20 minutes)

### 1. Create a GitHub repo
- Go to github.com → New repository → name it e.g. `unqualified-blog` → Create.
- Upload everything in this folder to that repo (drag-and-drop works on
  github.com, or use `git init / git add . / git commit / git push` if you're
  comfortable with git).

### 2. Connect it to Netlify
- Go to netlify.com → sign up (free) → "Add new site" → "Import an existing
  project" → choose your GitHub repo.
- Build command: `npm run build`
- Publish directory: `_site`
- Click Deploy. Netlify will build your site and give you a live URL.

### 3. Turn on Netlify Identity + Git Gateway (this powers the login for /admin)
- In your Netlify site dashboard: **Site configuration → Identity → Enable Identity**.
- Under Identity settings, set **Registration** to "Invite only" (so random
  people can't sign up to your admin panel).
- Still in Identity settings, scroll to **Services → Git Gateway → Enable Git Gateway**.
- Go to **Identity → Invite users**, invite your own email address.
- Check your email, accept the invite — it'll ask you to set a password.

### 4. Publish
- Visit `https://YOUR-SITE-NAME.netlify.app/admin`
- Log in with the email/password you just set
- Click **New Post**, fill in the fields, hit **Publish**
- Netlify rebuilds the site automatically (~1 minute) and your post goes live

## Day-to-day: creating, editing, deleting posts
All of it happens at `/admin`:
- **Create**: New Post → fill in title, date, category, cover image, excerpt, body → Publish
- **Edit**: click any post in the list → change it → Publish
- **Delete**: open the post → the menu next to Publish has a Delete option

## Local preview (optional, needs Node.js installed)
```
npm install
npm start
```
Then open http://localhost:8080

## Project structure
```
content/posts/     → your blog posts (Markdown, edited via /admin)
_includes/          → page templates (base layout + single-post layout)
index.njk            → homepage (hero, featured post, post grid, about, subscribe)
css/style.css        → all site styling
admin/               → the Decap CMS editor and its config
```
