# agudah.si — Agudas Yisroel of Staten Island

Static holding site, built to satisfy Google for Nonprofits domain verification
for AGUDAS YISROEL OF STATEN ISLAND on the domain `agudah.si`.

No build step. Plain HTML + one CSS file. Deploys as-is to GitHub Pages.

## Content status

Confirmed by the treasurer and in use on the site:

| Field   | Value                                        |
|---------|----------------------------------------------|
| Name    | Agudas Yisroel of Staten Island               |
| Rav     | Rabbi Moshe Klein, shlita                     |
| Address | 46 Birchard Avenue, Staten Island, NY 10314   |
| Phone   | (718) 283-4280                                |
| EIN     | 39-4600238                                    |
| Status  | 501(c)(3), IRS determination letter on file   |
| Emails  | info@ / gabbai@ / treasurer@ agudah.si        |

"Bais Eliezer" is an old name and appears nowhere on the site.

Minyan and shiur times are taken from the shul's own *Zemanei Tefila 5786* sheet
(Parshas Re'eh) at siagudah.weebly.com. Fixed times are printed; anything that moves
with the zmanim says "see weekly sheet" and links there.

Still to confirm:

- **Hebrew masthead: אגודת ישראל – סטעטן איילענד** — appears in all 5 files.
- **Krias haTorah on Monday and Thursday** (minyanim.html) — assumed, not on the sheet.

Seasonal shiurim: Pirkei Avos runs Pesach to Rosh Hashana; Chaim Ozer father-son
runs in the winter. Both are labelled as such rather than listed year-round.

Outbound links used: siagudah.weebly.com (weekly zmanim + monthly calendar),
shulspace.org/aysi, shulspace.org/aysi/donationForm. FideliPay is NOT used —
that link is dead.

## Deploy — GitHub Pages

1. New repo under the shul's GitHub account, e.g. `agudah-si-site`, public.
2. Push these files to the repo root (`CNAME` and `.nojekyll` included).
3. Settings → Pages → Source: *Deploy from a branch*, branch `main`, folder `/ (root)`.
4. Settings → Pages → Custom domain: `agudah.si` → Save.
5. Add DNS at Dynadot (see below).
6. Once DNS resolves, tick **Enforce HTTPS** in Settings → Pages.

## DNS at Dynadot

Set the nameservers to Dynadot's own, then use **Domain → DNS Settings**.

Apex `agudah.si` — four A records:

```
185.199.108.153
185.199.109.153
185.199.110.153
185.199.111.153
```

Optional AAAA records for IPv6:

```
2606:50c0:8000::153
2606:50c0:8001::153
2606:50c0:8002::153
2606:50c0:8003::153
```

Subdomain `www` — CNAME to `<github-account>.github.io`

Source: GitHub Docs, "Managing a custom domain for your GitHub Pages site".
Verify these are still current before entering them.

**Do not remove or overwrite MX records.** The A records above serve the website;
Google Workspace mail for `agudah.si` uses separate MX records. They coexist.

## Files

```
index.html      Home — schedule board hero
minyanim.html   Full davening schedule
shiurim.html    Learning schedule
about.html      Organisation details + explicit domain-ownership statement
contact.html    Address, emails, giving
assets/style.css
CNAME           Contains: agudah.si
.nojekyll       Stops Jekyll processing on GitHub Pages
```
