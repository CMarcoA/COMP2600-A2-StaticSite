# COMP2600-A2-SITE

This project is a personal resume website built with Pelican.

## Requirements

- Python 3.10+ (or any Python 3 version supported by your environment)
- `pip`

## Setup

From the project root:

```powershell
cd "d:\COMP2600\Assignment2\COMP2600-A2-SITE"
python -m venv .venv
.\.venv\Scripts\Activate.ps1
pip install pelican markdown
```

If `python` does not work, use `py` instead.

## Build the site

```powershell
python -m pelican content -o output -s pelicanconf.py
```

## Run locally

```powershell
python -m http.server 8000 -d output
```

Open <http://localhost:8000> in your browser.

## Update content

Edit files in `content/`, then rebuild:

```powershell
python -m pelican content -o output -s pelicanconf.py
```

Refresh your browser to see changes.
