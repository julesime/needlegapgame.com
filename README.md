# Needle Gap Reflex Website

Static public website for the iOS app **Needle Gap Reflex** at `https://needlegapgame.com`.

The site is intentionally minimal for App Store submission:

- Privacy policy at `/privacy`
- Support page at `/support`
- Simple home page at `/`
- No JavaScript
- No analytics
- No cookies
- No ads
- No third-party embeds
- No contact form backend

## Local Preview

Run a static server from the repository root:

```sh
python3 -m http.server 4173
```

Then open:

- `http://localhost:4173/`
- `http://localhost:4173/privacy`
- `http://localhost:4173/support`
- `http://localhost:4173/robots.txt`
- `http://localhost:4173/sitemap.xml`

## Recommended Deploy: GitHub Pages

1. Create a GitHub repository for this folder.
2. Push the site files to the `main` branch.
3. In GitHub, open the repository settings.
4. Go to **Pages**.
5. Set **Build and deployment** to **Deploy from a branch**.
6. Select branch `main` and folder `/ (root)`.
7. Save.
8. In **Custom domain**, enter `needlegapgame.com`.
9. Keep **Enforce HTTPS** enabled once GitHub allows it.

The `CNAME` file is already included for GitHub Pages and contains:

```txt
needlegapgame.com
```

Reference docs:

- GitHub Pages publishing source: <https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site>
- GitHub Pages custom domain DNS: <https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site/managing-a-custom-domain-for-your-github-pages-site>

## Alternative Deploy: Cloudflare Pages

1. Create a new Cloudflare Pages project.
2. Connect the GitHub repository.
3. Use these build settings:
   - Framework preset: `None`
   - Build command: `exit 0`
   - Build output directory: `.`
4. Deploy the project.
5. Add the custom domain `needlegapgame.com` in Cloudflare Pages.
6. Follow Cloudflare's shown DNS target values.

Reference docs:

- Cloudflare Pages static HTML: <https://developers.cloudflare.com/pages/framework-guides/deploy-anything/>

## Alternative Deploy: Netlify

1. Create a new Netlify site from the GitHub repository.
2. Use these build settings:
   - Build command: leave empty
   - Publish directory: `.`
3. Deploy the site.
4. Add the custom domain `needlegapgame.com` in Netlify.
5. Follow Netlify's shown DNS target values.

Reference docs:

- Netlify build settings: <https://docs.netlify.com/build/configure-builds/overview/>

## Namecheap DNS Setup

Use the DNS values from your selected host. The records below are for the recommended GitHub Pages setup.

In Namecheap, set TTL to `Automatic` unless you have a reason to choose a custom TTL.

| Type | Host | Value | Notes |
| --- | --- | --- | --- |
| A | `@` | `185.199.108.153` | GitHub Pages apex IPv4 |
| A | `@` | `185.199.109.153` | GitHub Pages apex IPv4 |
| A | `@` | `185.199.110.153` | GitHub Pages apex IPv4 |
| A | `@` | `185.199.111.153` | GitHub Pages apex IPv4 |
| AAAA | `@` | `2606:50c0:8000::153` | Optional GitHub Pages apex IPv6 |
| AAAA | `@` | `2606:50c0:8001::153` | Optional GitHub Pages apex IPv6 |
| AAAA | `@` | `2606:50c0:8002::153` | Optional GitHub Pages apex IPv6 |
| AAAA | `@` | `2606:50c0:8003::153` | Optional GitHub Pages apex IPv6 |
| CNAME | `www` | `<github-username>.github.io` | Do not include the repository name |

Namecheap path:

1. Sign in to Namecheap.
2. Go to **Domain List**.
3. Select `needlegapgame.com`.
4. Open **Advanced DNS**.
5. Remove conflicting parking, URL redirect, or old website records for `@` and `www`.
6. Add the records required by your selected host.
7. Save changes.
8. Wait for DNS propagation.

GitHub notes that DNS propagation can take up to 24 hours.

After DNS resolves, verify:

- `https://needlegapgame.com/`
- `https://needlegapgame.com/privacy`
- `https://needlegapgame.com/support`

Reference docs:

- Namecheap host records: <https://www.namecheap.com/support/knowledgebase/article.aspx/434/2237/how-do-i-set-up-host-records-for-a-domain/>
