# Website

Static academic site: three HTML pages and one stylesheet, no build step.

    index.html      home: bio, links, selected research
    papers.html     all papers and work in progress
    cv.html         embeds assets/Williams_CV.pdf
    assets/         site.css, kian.jpg (portrait), Williams_CV.pdf
    papers/         PDFs linked from the papers pages
    .nojekyll       tells GitHub Pages to serve the files as they are

## Before publishing

- Remove the `noindex` meta line from each page when you want search engines to list the site.
- Replace assets/Williams_CV.pdf with the final CV (same filename, nothing else to change).
- Check the bio and paper summaries match your statements.

## Publish on GitHub Pages

1. Create an empty public repository on GitHub named `kian-williams.github.io`.
2. In Terminal:

       cd "/Users/kianwilliams/Documents/PhD Application Materials/Website"
       git init
       git add .
       git commit -m "Initial site"
       git branch -M main
       git remote add origin https://github.com/kian-williams/kian-williams.github.io.git
       git push -u origin main

3. On GitHub: Settings → Pages → Source: "Deploy from a branch", branch `main`, folder `/ (root)`. The site appears at https://kian-williams.github.io within a few minutes.

## Optional: custom domain

1. Buy a domain (e.g. kianwilliams.com) from any registrar.
2. At the registrar, add four A records for `@` pointing to 185.199.108.153, 185.199.109.153, 185.199.110.153, 185.199.111.153, and a CNAME record for `www` pointing to `kian-williams.github.io`.
3. On GitHub: Settings → Pages → Custom domain: enter the domain, save, then tick "Enforce HTTPS" once the check passes.
4. GitHub writes a `CNAME` file into the repo. Keep it.

## Updating

Edit a file, then from this folder run:

    git add -A
    git commit -m "Describe the change"
    git push

The live site updates within a minute or two. Where things live:

- Bio, email, links, the two research entries on the home page: index.html
- Full papers list and summaries: papers.html (copy an existing `<article class="paper">` block to add one)
- CV: drop a new PDF over assets/Williams_CV.pdf, keep the filename, and update the "Last updated" line in cv.html
- Photo: replace assets/kian.jpg (4:5 portrait, about 1200 x 1500 px)
- Colours, column width, fonts: the variables at the top of assets/site.css
- Paper PDFs: put them in papers/ and link them from a `<p class="files">` line
- Nav, header, footer: repeated in each of the three HTML files, so change all three

To check a change before pushing, open index.html in a browser. To see what you changed since the last push: `git status` and `git diff`.

The original 7.8 MB photo (assets/IMG_1200_original.JPG) is listed in .gitignore and stays off GitHub.
