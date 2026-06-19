# Mikdar legal pages

Static HTML for Mikdar's Privacy Policy, Terms of Service, Account
Deletion request page, and a tiny landing page that links to all three.

These pages are what you give to Google Play Console as the
**Privacy Policy URL**, **Terms of Service URL**, and
**Account deletion URL** when you submit Mikdar to the store.

---

## What's in this folder

| File | Purpose | URL slug after publishing |
| --- | --- | --- |
| `index.html` | Landing page with links to all three documents | `/` (root) |
| `privacy.html` | Privacy Policy | `/privacy.html` |
| `terms.html` | Terms of Service | `/terms.html` |
| `delete-account.html` | Web-based account deletion request page | `/delete-account.html` |

All files are self-contained — no JavaScript, no fonts to load, no
external assets. Open any of them in a browser locally to preview.

---

## Step-by-step: publish on GitHub Pages (≈ 5 minutes)

You'll end up with three live URLs you can hand to Play Console:

```
https://<your-github-username>.github.io/mikdar-legal/privacy.html
https://<your-github-username>.github.io/mikdar-legal/terms.html
https://<your-github-username>.github.io/mikdar-legal/delete-account.html
```

### 1. Create a new GitHub repository

1. Go to https://github.com/new
2. **Repository name**: `mikdar-legal` (this becomes part of the URL)
3. **Visibility**: choose **Public** (GitHub Pages on free accounts only
   serves public repos)
4. Leave everything else unticked (no README, no .gitignore, no licence
   — we already have files locally)
5. Click **Create repository**

### 2. Push these files to the repo

Open a terminal in this folder (`D:\Dev\mikdar-legal`) and run:

```bash
git init
git add .
git commit -m "Initial legal pages for Mikdar Play Store submission"
git branch -M main
git remote add origin https://github.com/<your-github-username>/mikdar-legal.git
git push -u origin main
```

Replace `<your-github-username>` with your actual GitHub username.

> If `git push` asks for credentials, use a
> [personal access token](https://github.com/settings/tokens) as the
> password (GitHub no longer accepts your account password over HTTPS).

### 3. Turn on GitHub Pages

1. Open your new repo on github.com.
2. Click **Settings** (top tab).
3. Click **Pages** in the left sidebar.
4. Under **Build and deployment** → **Source**, choose
   **Deploy from a branch**.
5. Under **Branch**, choose **main** and folder **/ (root)**, then click
   **Save**.
6. Wait about 1 minute. Refresh the page.
7. GitHub will show a green box at the top with your live URL:
   `https://<your-github-username>.github.io/mikdar-legal/`

### 4. Test the live URLs

Open each of these in a browser and confirm the page loads:

- `https://<your-github-username>.github.io/mikdar-legal/` → landing page
- `https://<your-github-username>.github.io/mikdar-legal/privacy.html`
- `https://<your-github-username>.github.io/mikdar-legal/terms.html`
- `https://<your-github-username>.github.io/mikdar-legal/delete-account.html`

If a link doesn't work, double-check the spelling in the URL exactly
matches the filename (case-sensitive on GitHub Pages).

### 5. Put the URLs into Play Console

When you submit Mikdar:

| Play Console field | Paste this URL |
| --- | --- |
| App content → **Privacy Policy** | `https://<you>.github.io/mikdar-legal/privacy.html` |
| App content → **Account deletion** → URL | `https://<you>.github.io/mikdar-legal/delete-account.html` |
| Store listing → **Terms of Service** (optional but recommended) | `https://<you>.github.io/mikdar-legal/terms.html` |

---

## Updating the pages later

Whenever you change one of the HTML files:

1. Edit the file locally.
2. Bump the "Last updated" date inside the file (search for `Last updated`).
3. Commit and push:

```bash
git add .
git commit -m "Update privacy policy: <one-line reason>"
git push
```

GitHub Pages rebuilds automatically in about 30 seconds. No further
action needed.

---

## A note on the contact email

Every file currently lists `info@ezomfy.com` as the contact
address. That's fine for launch, but if you ever want a dedicated
support inbox (e.g. `support@mikdar.app`), do a find-and-replace across
all four HTML files and push the change.

---

## A note on the email button on the deletion page

The "Email a deletion request" button on `delete-account.html` opens
the user's default mail client with a pre-filled subject and body. If
the user doesn't have a mail client configured, they can still copy
the address shown directly below the button.
