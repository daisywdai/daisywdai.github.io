# daisywdai.com

Source of Weijia (Daisy) Dai's academic website, served by GitHub Pages from the `main` branch of this repository. Plain HTML and CSS, no build step, no scripts.

The look is plain: a white page, one centered column, the name at the top left with the navigation beside it and one thin rule below, Merriweather for body text, Figtree for the name, navigation, and headings, navy links. Papers are listed inline as "Title, with coauthors. Journal, details." with an abstract that opens on click.

## Layout

```
index.html            home page
research/index.html   papers, by status
teaching/index.html   courses and syllabi
style.css             the only stylesheet
fonts/                the two typefaces, served from this site, with their licenses
s/                    every PDF the site links to (CV, papers, appendices, syllabi)
images/               the photo: photo-dai.jpg (250x333) and photo-dai-2x.jpg (500x666, for sharp screens), both without camera metadata
main/index.html       redirect from the old /main address to the home page
404.html              not-found page
.nojekyll             tells GitHub Pages to serve the files as they are
```

## Rules

- Keep the file names in `s/` stable. Every PDF link on the site has the form `/s/<file>.pdf`, which is the form the previous host used, so links in Google Scholar, old emails, and applications keep working. Replace a file in place to update it; add a new file for a new paper.
- The CV and the papers are compiled elsewhere. Copy the finished PDF into `s/` under the existing name.
- Edit the HTML directly. Each page is self-contained and under 150 lines.
- Each abstract on the research page is a `<details class="abstract">` block under its paper, with the text taken from the first page of the PDF the title links to. When a paper's PDF is replaced, check its abstract and update the text if it changed. To add an abstract, copy an existing block.
- The text size is set in one place, `--size` near the top of `style.css`.
- The site name is "Weijia (Daisy) Dai" everywhere it shows. The home page head also carries a small block of search-engine data (`application/ld+json`, not a script that runs) that lists "Weijia Dai" as the name and "Daisy Dai" as an alternate name, so searches for either find the site. Update its `jobTitle` and `affiliation` when the job changes.
- In published papers, the italic journal name links to the paper's DOI (the version of record); the title links to the free PDF in `s/`.

## Publishing

```
git add -A
git commit -m "Describe the change"
git push
```

GitHub Pages rebuilds within a few minutes. Check the live site afterwards.

## Domain

The domain daisywdai.com is registered at Squarespace (renews August 17 each year). It points at this site through DNS records in the Squarespace domain panel: four `A` records for the apex to GitHub Pages' addresses, a `CNAME` for `www` to `daisywdai.github.io`, and a `TXT` verification record. The custom domain is set in the repository's Settings, Pages, which also writes the `CNAME` file in this repository. Do not delete that file once it exists.
