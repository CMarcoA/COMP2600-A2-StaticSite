# Resume Website README (Draft / Incomplete) - GitHub Pages + Pelican

## Purpose

This README (draft) describes how I formatted my resume in **Markdown** and published it as a **static website** using **Pelican** and **GitHub Pages**.

Workflow to ideas from Andrew Etter’s *Modern Technical Writing*: 
- write in plain text
- keep content separate from presentation
- treat documentation like code (version control)
- make publishing repeatable through automation.

## Prerequisites
- Git + a GitHub account
- Python 3 + pip
- Terminal (PowerShell/Terminal)
- Pelican installed (usually in a virtual environment)

## Instructions (Draft)
### 1) Create the project (Etter: “make the process repeatable”)
1. Create a new folder for the project (example: `resume-site/`).
2. Initialize Git: `git init`
3. Create a GitHub repository and add it as a remote

### 2) Set up Pelican (Etter: “separate content from tools”)
4. Create and activate a virtual environment `$env:VIRTUAL_ENV`
5. Install Pelican: `pip install pelican`
6. Run `pelican-quickstart` and choose basic options (site name, URL, etc.)
7. Check `pelicanconf.py` and set the site title and any page settings

### 3) Write the resume in Markdown (Etter: “plain text wins”)
8. Create a resume page like `content/pages/resume.md`.
9. Use headings for sections (Education / Experience / Projects).
10. Use bullet points for achievements, keeping each bullet specific and easy to scan.


### 4) Build + preview locally
11. Build the site (one of these, depending on setup):
    - `pelican content -o output -s pelicanconf.py`  
    - or `make html` (if Pelican created a Makefile)
12. Serve locally:
   - `pelican --listen`  
   - or `make serve`
13. Open the local URL and check formatting, spacing, and navigation


### 5) Publish on GitHub Pages (“automate publishing”)
14. Commit your source changes: `git add .` then `git commit -m "Add resume content"`
15. Generate the site into `output/`.
16. Deploy `output/` to a `gh-pages` branch (common approach):
17. In the repo settings, enable **GitHub Pages** to serve from `gh-pages`


## Further resources / readings (Incomplete)
- Pelican docs: https://docs.getpelican.com/
- GitHub Pages docs: https://docs.github.com/en/pages

## FAQ (Draft)
**Why use Markdown instead of writing raw HTML?**  
Markdown is faster to write, easier to edit, and cleaner to track in Git. Pelican converts it to HTML automatically

**I updated `resume.md`, why don’t I see changes on the live site?**  
Usually: I forgot to rebuild the site, I didn’t deploy the new `output/` to `gh-pages`, Pages is pointed at the wrong branch, or my browser cached the old version.

## Credits (Incomplete)
- README + resume content: Claudius Marco Andrew
- Tools: Pelican + GitHub Pages
- Theme/assets: default