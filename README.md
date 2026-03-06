# Resume Website README - GitHub Pages + Pelican

## Purpose

This README (draft) describes how I formatted my resume in **Markdown** and published it as a **static website** using **Pelican** and **GitHub Pages**.

Workflow to ideas based from Andrew Etter’s Modern Technical Writing: 
- write in plain text
- keep content separate from presentation
- treat documentation like code (version control)
- make publishing repeatable through automation.

## Prerequisites
- Git installed + a GitHub account
- A text editor for Markdown (VS Code or similar)
- Python 3 + pip installed
- Terminal (PowerShell/Terminal)
- Pelican installed (usually in a virtual environment)


## Instructions (Draft)
### 1) Create the project (Etter: “make the process repeatable”)
1. Create a new folder for the project (example: `resume-site/`).
2. Initialize Git: `git init`
3. Create a GitHub repo and add it as a remote

### 2) Set up Pelican (Etter: “separate content from tools”)
4. Create and activate a virtual environment 
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


## FAQ 
**Why use Markdown instead of writing raw HTML?**

Markdown is better tool in this case because it lets us focus on the content of the resume rather than the code that implements it, it’s very difficult to get distracted from programming and readjusting the code to fit the details and designs of the webpage. Instead of writing a large amount of HTML code for every heading, list, and paragraph, we can write in a simpler plain text format that is easier to read and edit. Not only that, but one of Andrew Etter’s idea regarding technical writing is that technical writers should work in more lightweight markup and keep content separate from presentation. In this project, writing the resume content in Markdown first, and then Pelican would convert that content into HTML for the website. That means we did not need to manually build every webpage element ourselves.
In the long run, markdown is also easier to maintain over time. If we need to update a particular section for example: education, experience, or skills later, I can open one text file, change the wording, save it, and rebuild the site. 
Because the file is plain text, it also works hand in hand with Git. For a resume website, a useful feature is tracking changes, because resumes often change in small but important ways. Git can clearly show what lines changed between versions, which makes the editing process easier to track. 
Overall, Markdown is a better choice here because it is simpler, faster to edit, easier to version control, and more consistent with the workflow recommended in Modern Technical Writing.


**The resume.md file was updated, so why are the changes not visible on the live website?**

I updated resume.md, so why do I not see the changes on the live website?
Upon further research, there are multiple common reasons for this problem. The most likely reason is that editing the Markdown file does not automatically update the published website. One rule of thumb is to first, rebuild the site so that Pelican generates a new HTML version from the updated Markdown. If we skip that step, the website will still be showing the old, generated files. After rebuilding, the next step is to showcase the site, and we need to make sure that the updated output is deployed to GitHub Pages, not the old one. If the new files were only changed on our computer and not pushed to the correct branch or publishing location, the live site will not change.
Another possible reason is that GitHub Pages may still be pointing to the wrong branch or folder in the repository settings. For example, if Pages is set to publish from gh-pages, but I only pushed changes to main, the live site may still show the older version. The browser can also make it seem like nothing changed, even when the site was updated correctly. In that case, refreshing the page more forcefully or opening the site in a private browsing window can help. A good troubleshooting order is: 
1. save the Markdown file
2. rebuild the site
3. confirm the generated files changed
4. commit the changes
5. push them to the correct branch
6. check the GitHub Pages settings


## Further resources / readings

- [Pelican Documentation](https://docs.getpelican.com/)
- [GitHub Pages Documentation](https://docs.github.com/en/pages)
- [Markdown Guide](https://www.markdownguide.org/)
- [More on Andrew Etter (author of Modern Technical Writing)](https://andyetter.com/)

## Credits

- README + resume content: Claudius Marco Andrew
- In-class peer review contributors: Ashley Davis Kosasih
- Tools used: Pelican, Git, and GitHub Pages
- Theme/assets: Pelican default theme
- Third-party material: None
