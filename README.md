# `rypyrx`

reproducible research environments, cross language/cross-platform

[![Open in GitHub Codespaces](https://github.com/codespaces/badge.svg)](https://codespaces.new/knaaptime/rypyrx)

pronounced 'rip-rex', like [reprex](https://reprex.tidyverse.org/), but so that R people can grok reproducible Python environments for papers et al

tl;dr: I write in quarto and do my work in both Python and R. I work with lots of people who are new to Python environments, or hate them altogether. I swear they are straightforward for this task now!

the important pieces are:

- the `pixi.toml` file defines the dependencies and when installed pixi creates a lockfile to make sure you can re-create that *exact* environment anywhere
- the files in `.devcontainer` setup codespaces to install the project dependencies and some useful vscode extensions (so you can run whatever notebooks you create in the cloud)
- the files in `.github/workflows` setup the repo to serve a static website from the `slides` directory, so when you use quarto to generate slides in that directory, they're available immediately at `<{your-github}.github.io/{project_name}>` 
  - the slides and paper are separate quarto projects which allows you to keep the repo private while you work on code and paper, but publish the slides (using the same materials) for giving conference talks etc while the paper is in draft.

## Goals

- reproducible python/R environments
  - one-click launch in the cloud
  - consistent cross-platform local environments
- write in quarto markdown 
- include slides


## Install and Run

To run locally:

- clone this repository, follow below

To run in codespaces:

- click the 'open in codespaces' button above
  - the default config will include at least 4 cores (dont go below 16gb memory), but you can crank it up for better performance

`pixi install`

`cd notebooks` (not strictly necessary, but its better to launch jlab from inside the notebooks dir)
`pixi run jupyter lab`

if running in a codespace this starts a jupyter server on the VM's 'localhost'.
Open an existing notebook (or start a new one). When selecting a kernel, choose
'Existing jupyter server' and copy/paste the URL with token from the terminal

edit the notebooks as you like

## Execute and Build

`cd paper`  
`pixi run quarto render`

will run the python and r noteooks and generate the html and pdf in `paper/_manuscript`

**note** this workflow works perfectly when run locally (on my mac). Currently, quarto's default latex engine (tinytex) has a `PATH` issue when running through pixi in codespaces (which, given pixi's hyper-sandboxing, is not terribly surprising). You can get around that at the moment by using the tectonic engine for the pdf, like:

`pixi run quarto render --pdf-engine tectonic`

you can use `pixi run quarto preview` to preview while you work

