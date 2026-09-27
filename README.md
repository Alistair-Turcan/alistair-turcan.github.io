# Alistair Turcan — academic website

A complete single-page website in plain HTML and CSS. There is no JavaScript,
package manager, theme, or build step to maintain.

Home and Papers jump to sections of the same page. CV opens the included PDF in
a new browser tab. The page contains all 19 publications from the supplied CV:
14 key-author publications and 5 other publications. Seventeen entries have
paper links copied from the PDF; the two in-preparation entries have no invented
links. Your name is emphasized in each author list.

## Files

index.html               The full website, including all CSS and content.
Alistair_Turcan_CV.pdf    The exact PDF supplied in this conversation.
.nojekyll                Empty file to bypass Jekyll processing.
README.md                These instructions (not required to display the site).

## Before uploading

The bundled PDF is unchanged. It still contains your phone number, education,
experience, and referees' email addresses. The website itself has no positions,
education, or news section. Review the PDF for public sharing and, as needed,
replace it with a public-facing copy using the same filename before uploading.

The HTML includes your email, Scholar profile, website address, and CV links.
No headshot, GitHub profile, Twitter profile, or ORCID was supplied in the CV, so
none has been invented. Additional profile links can be added in the marked
profile-links block.

## Preview locally

1. Unzip the package into a folder.
2. Double-click index.html to open it in a browser.
3. Keep the PDF in the same folder to make the CV links work.

A local server is optional, not required. To use one, open a terminal in the
folder and run:

    python -m http.server 8000

Then open http://localhost:8000/ and stop the server with Ctrl+C.

## Publish on GitHub Pages (browser-only method)

1. Sign in to the GitHub account that will own the site. Your CV lists
   https://alistair-turcan.github.io/, so the instructions below assume that
   your username is alistair-turcan. For a different account, substitute its
   lowercase username and also update the canonical and profile URLs in HTML.
2. Open your alistair-turcan.github.io repository, or create a public repository
   with that exact name. When creating one, enable Add README so that the main
   branch exists. Keep a backup of an existing site before replacing its files.
3. Select Add file -> Upload files. Upload the extracted index.html and
   Alistair_Turcan_CV.pdf to the repository root. Upload the individual files,
   not the ZIP or an enclosing folder. Commit the changes to main. README.md
   is optional; do not overwrite an existing README unless intended.
4. Include the empty .nojekyll file at the repository root. It can be hidden by
   your file manager. Alternatively, use Add file -> Create new file on GitHub,
   name it .nojekyll, leave the body empty, and commit. Plain HTML also works
   without it; the file makes the intended no-build setup explicit.
5. Open Settings -> Pages. Under Build and deployment select:

       Source: Deploy from a branch
       Branch: main
       Folder: /(root)

   Click Save. Use the branch containing your files when it is not called main.
6. Allow up to 10 minutes for publishing, then open:

       https://alistair-turcan.github.io/

   Settings -> Pages also provides a Visit site link. If this is a project
   repository rather than your username.github.io repository, use the URL
   that GitHub shows in Settings -> Pages.

The minimum layout is:

    alistair-turcan.github.io/
    ├── index.html
    ├── Alistair_Turcan_CV.pdf
    └── .nojekyll

## Edit the website

- Bio and contact links: search index.html for HOME: EDIT BIO AND LINKS HERE.
- Research topics: edit the two research-topic blocks.
- Papers: search for PAPERS: EDIT PUBLICATIONS HERE. Each publication is a
  separate <li class="publication">. Duplicate an entry in the correct group,
  give it a unique id, and edit its title, authors, URL, venue, year, and status.
  The ordered-list numbering updates automatically; IDs do not control order.
- Contribution marks: use <sup>*</sup> or <sup>†</sup> after an author's name.
  Keep the key at the top of the Papers section.
- CV: replace Alistair_Turcan_CV.pdf, preserving its spelling and capitalization.
  The HTML bibliography does not automatically sync with a replacement CV;
  update it separately when papers or statuses change.
- Photo: upload a portrait called headshot.jpg to the same folder, then remove
  the surrounding comment markers from the OPTIONAL PHOTO block. The CSS for
  the photo is already included. No broken image is displayed without a photo.
- Colors and width: edit the variables at the beginning of the <style> block.

Commit changes to the configured publishing branch to update the live site.
No npm install, React, Jekyll theme, or custom deployment workflow is necessary.

## Troubleshooting

- A 404 at the home URL: check the repository name, that index.html is directly
  at the publishing root, and the branch/folder selected in Settings -> Pages.
- CV gives a 404: upload the PDF to the same directory as index.html and make
  its filename match Alistair_Turcan_CV.pdf exactly, including capitalization.
- An old page appears: allow publishing to finish, inspect the deployment in
  the Actions tab, and then refresh or check in a private browser window.
- Existing framework site: switching the publishing source can replace the
  old deployment. Keep a backup. Existing custom-domain settings may cause
  GitHub to publish or redirect to that domain instead of the github.io URL.

## Source and editorial notes

Content source: the supplied Alistair_Turcan_CV.pdf. The research introduction,
research interests, author ordering, equal-contribution and co-senior markers,
publication groupings, venues, years, review statuses, and paper URLs are drawn
from that document. Titles and author lists are not replaced with metadata from
external searches. Review and submission labels are not acceptance claims.
The two manuscripts without a year in the CV are kept without an invented year.
The breast-cancer entry retains the CV's abbreviated author list (ellipsis).
Some supplied paper links point to preprints rather than final venue pages.
External destinations and publication status have not been independently
verified; review them before publishing. The site makes no unsupported claim
that you hold a faculty appointment or have already completed the Ph.D.

Layout reference requested by the user:
https://martinjzhang.github.io/

Official GitHub documentation used for deployment instructions:
https://docs.github.com/en/pages/quickstart
https://docs.github.com/en/pages/getting-started-with-github-pages/creating-a-github-pages-site
https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site
