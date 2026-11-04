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

Edit the HTML, then `git add . && git commit -m "Update" && git push`. Changes are live within a minute or two.

Keep assets/IMG_1200_original.JPG out of the repo if you prefer: it is the 7.8 MB original. Add a `.gitignore` line for it.
