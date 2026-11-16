# daisywdai.com

Source of Weijia (Daisy) Dai's academic website, served by GitHub Pages from the `main` branch of this repository. Plain HTML and CSS, no build step, no scripts.

The look follows the site's earlier design: a light gray bordered canvas, the name and navigation centered in letter-spaced capitals, Merriweather for body text, Figtree for headings, navy links. Papers are listed inline as "Title, with coauthors. Journal, details."

## Layout

```
index.html            home page
research/index.html   papers, by status
teaching/index.html   courses and syllabi
style.css             the only stylesheet
fonts/                the two typefaces, served from this site, with their licenses
s/                    every PDF the site links to (CV, papers, appendices, syllabi)
images/               the photo
main/index.html       redirect from the old /main address to the home page
404.html              not-found page
.nojekyll             tells GitHub Pages to serve the files as they are
```

## Rules

- Keep the file names in `s/` stable. Every PDF link on the site has the form `/s/<file>.pdf`, which is the form the previous host used, so links in Google Scholar, old emails, and applications keep working. Replace a file in place to update it; add a new file for a new paper.
- The CV and the papers are compiled elsewhere. Copy the finished PDF into `s/` under the existing name.
- Edit the HTML directly. Each page is self-contained and under 150 lines.

## Publishing

```
git add -A
git commit -m "Describe the change"
git push
```

GitHub Pages rebuilds within a few minutes. Check the live site afterwards.

## Domain

The domain daisywdai.com is registered at Squarespace (renews August 17 each year). It points at this site through DNS records in the Squarespace domain panel: four `A` records for the apex to GitHub Pages' addresses, a `CNAME` for `www` to `daisywdai.github.io`, and a `TXT` verification record. The custom domain is set in the repository's Settings, Pages, which also writes the `CNAME` file in this repository. Do not delete that file once it exists.
