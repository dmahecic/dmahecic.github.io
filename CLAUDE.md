# CLAUDE.md: notes for working on Dora Mahecic's personal site

## What this repo is
- `dmahecic/dmahecic.github.io` is the personal website, served at https://dmahecic.github.io by GitHub Pages from `main`.
- It is one hand-written static page, `index.html`, with inline CSS, no framework and no build step. `.nojekyll` turns off Jekyll.
- Pushing to `main` publishes the site. It usually goes live in 1–2 minutes. Check it with
  `curl -s "https://dmahecic.github.io/?cb=$RANDOM" | grep '<title>'`.
- A second repo, **`dmahecic/dmahecic`**, holds only `README.md`, the intro card at the top of https://github.com/dmahecic. Keep it in sync when the role, papers or links change.

## Facts (verified Nov 2026)
- **Role:** Research Associate, Paulsson lab, Department of Systems Biology, Harvard Medical School. Use this exact wording, never "postdoc". It matches the GitHub bio.
- **PhD:** EPFL (Switzerland), with Prof. Suliana Manley (Laboratory for Experimental Biophysics).
- **Research:** plasmid replication control (current, using microscopy and microfluidics); high-throughput super-resolution (mfFIFI, iSIM); adaptive, event-driven microscopy; mitochondrial dynamics and membrane tension; centriole architecture.
- **ORCID:** 0000-0003-1004-4771
- **Google Scholar:** https://scholar.google.com/citations?user=FAnKd20AAAAJ
- **X/Twitter:** @Dora_Mahecic
- **Code repos:** `EDA` (event-driven acquisition tools) and `simmla_w_mfFIFI` (Köhler integrator wave-optics simulations).
- **Watch out:** PubMed's `Mahecic D[Author]` search also returns diabetes papers by a different Mahecic (Davorka Herman Mahecic). Exclude them.

## Page structure (`index.html`)
- `<head>`: title, meta description, Open Graph tags and a JSON-LD `Person` block. Update `jobTitle`, `affiliation` and `sameAs` there when the role or links change.
- The colour scheme is defined once as CSS variables in `:root`, with a dark-mode override.
- The sections are `#about`, `#research` (cards), `#publications` and `#contact`.
- The profile photo is `https://github.com/dmahecic.png`, so changing the GitHub avatar updates the site.
- The link buttons in the header are `<a class="chip">`. A commented-out Bluesky button is ready to fill in.

## Adding a publication
Add an item at the top of `<ol class="pubs">`, newest first, and wrap Dora's name in `<span class="me">`:
```html
<li><div class="pub-title"><a href="https://doi.org/DOI">Title</a></div>
    <div class="pub-meta">First A, <span class="me">Mahecic D</span>, … Last Z · <em>Journal</em> vol, pages (Year)</div></li>
```
For a preprint, put `<em>bioRxiv</em>` and the year, and add ` · Preprint` at the end. If the paper is a major first-author paper, also add it to "Selected papers" in the `dmahecic/dmahecic` README.

## Open ideas
- Add the first Paulsson-lab paper or preprint once it's out, and update the "Current" research card to match.
- Add a CV PDF (`cv.pdf`) and link it from the header buttons.
- Add a Bluesky handle if Dora has one.

## Working notes
- On Windows, clone with `git -c core.longpaths=true clone …` if the folder path is long.
- Commits are authored as `Dora Mahecic <dmahecic@users.noreply.github.com>`.
