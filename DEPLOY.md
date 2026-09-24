# legaltobuildbeautiful.com — GitHub Pages launch checklist

Domain registered at GoDaddy 24 September 2026, no protection add-ons. Hosting on GitHub
Pages, free. All files configured for **.com**.

```
index.html     the whole site, self-contained
CNAME          tells GitHub Pages which domain serves this repo
robots.txt     lets search engines index it
sitemap.xml    one URL, update lastmod when you revise
.nojekyll      skips Jekyll processing — faster builds, no surprises
```

No build step, no dependencies. Push and it serves.

---

## Before anything else — three things at GoDaddy, ten minutes

**1. Two-factor authentication, authenticator app not SMS.**
Account Settings → Login & PIN → 2-Step Verification. SIM-swap is the real attack against
domain owners and SMS doesn't stop it. Highest-value item here, costs nothing.

**2. Auto-renew on, card verified.**
This substitutes for the expiration protection you declined. Confirm the card outlives the
domain, and set a calendar reminder at eleven months — auto-renew fails silently when a card
lapses.

**3. Confirm transfer lock and WHOIS privacy are on.**
Both should be by default. Verify rather than assume — without privacy, your name and
address are public record attached to an advocacy site.

Do the same for your GitHub account: **enable 2FA there too.** Your domain and your site
content are now two separate things an attacker could go after.

---

## Step 1 — Create the repository

Public repo. GitHub Pages on private repos requires a paid plan, and the source here is
going on the public internet anyway — nothing in it is sensitive.

1. github.com → New repository
2. Name it something plain: `legaltobuildbeautiful` works
3. **Public**, no README, no .gitignore, no license (add one later if you want)
4. Create

Then upload the files. Easiest path, no terminal needed:

- On the empty repo page, click **uploading an existing file**
- Drag in `index.html`, `robots.txt`, `sitemap.xml`, `CNAME`
- Commit to `main`

⚠️ **`.nojekyll` and `CNAME` are easy to lose.** Files starting with a dot are hidden in
macOS Finder, so `.nojekyll` may not appear when you drag. Press **Cmd+Shift+.** in Finder
to show hidden files, then drag it in. If GitHub's uploader still refuses it, create it in
the browser instead: **Add file → Create new file**, name it `.nojekyll`, leave it empty,
commit.

## Step 2 — Turn on Pages

Repo → **Settings** → **Pages**

- Source: **Deploy from a branch**
- Branch: **main**, folder: **/ (root)**
- Save

Wait a minute or two. A green banner gives you a `username.github.io/legaltobuildbeautiful`
URL. Open it and confirm the page renders before touching DNS — if something's wrong, you
want to find out now rather than while chasing a DNS problem.

## Step 3 — Point the domain at GitHub

**At GoDaddy:** My Products → Domains → your domain → **DNS**.

First, **delete the parked records GoDaddy created**: there's a default `A` record on `@`
pointing at a GoDaddy parking IP, and usually a `CNAME` on `www` pointing to
`@` or a GoDaddy host. Both must go or they'll fight the new ones.

Then add these eight records for the apex domain:

| Type | Name | Value |
|---|---|---|
| A | @ | 185.199.108.153 |
| A | @ | 185.199.109.153 |
| A | @ | 185.199.110.153 |
| A | @ | 185.199.111.153 |
| AAAA | @ | 2606:50c0:8000::153 |
| AAAA | @ | 2606:50c0:8001::153 |
| AAAA | @ | 2606:50c0:8002::153 |
| AAAA | @ | 2606:50c0:8003::153 |

And one for `www`, so both spellings work:

| Type | Name | Value |
|---|---|---|
| CNAME | www | **your-username**.github.io |

Note the trailing `.github.io` — it's your GitHub username, not the repo name, and GoDaddy
may append a trailing dot on save. That's fine.

Leave TTL at whatever GoDaddy defaults to.

## Step 4 — Attach the domain in GitHub

Back in **Settings → Pages → Custom domain**, enter `legaltobuildbeautiful.com` and save.
GitHub runs a DNS check; it can fail for the first while as records propagate, which is
normal. Re-check after an hour.

Once the check passes, GitHub provisions a Let's Encrypt certificate. When the
**Enforce HTTPS** checkbox becomes available — usually within an hour, sometimes longer —
**tick it.** Don't announce the site before that box is ticked; an unencrypted policy paper
draws a browser warning that undoes the impression the page is built to make.

The `CNAME` file in the repo does the same job as the custom-domain field. Having both is
correct and they'll stay in sync.

---

## Four decisions still open in index.html

Search the file for `EDIT BEFORE LAUNCH`.

**1. Attribution.** The masthead reads "Working paper / September 2026 / Revision 1" with no
author and no institution. Add your name if you want it. Whether the Manhattan Institute's
name goes on this is for you and MI comms — I left it off rather than attach an
organization's name on my own judgment.

**2. Corrections mailbox — I'd treat this as a blocker.** The footer links
`corrections@legaltobuildbeautiful.com`, which doesn't exist. Free forwarding at GoDaddy
(My Products → Email → Forwarding) points it at your MI address in two minutes. A paper that
invites corrections and bounces them is worse than one that doesn't ask.

**3. Disclaimer.** If this is your work rather than an MI product, one line in the footer.

**4. Sitemap date.** Update `<lastmod>` when you revise.

---

## Updating the page later

Edit `index.html` in the GitHub web editor (open the file, click the pencil), commit, and
the change is live in about a minute. No deploy step. That's the main advantage of Pages
over dragging files at a host.

---

## After launch

- Submit the sitemap to Google Search Console
- Check it on a phone
- Paste the URL into Slack once to confirm the link preview renders — that's the Open Graph
  tags working

---

## Two loose ends

**The .org.** `legaltobuildbeautiful.org` was available last week. ~$12/year to stop someone
parking the obvious sibling of your domain. On a contested topic that's cheap, and it gets
harder to fix later.

**Open citations 1 and 2.** The Moynihan 1962 quotation and the Miami 21 height question sit
under arguments that are live on the page. Worth closing before the site gets traffic.
