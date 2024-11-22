# `rypyr`

[![Open in GitHub Codespaces](https://github.com/codespaces/badge.svg)](https://codespaces.new/knaaptime/rypyr)

pronounced 'ripper', like [repr](), but so that R people can grok reproducible Python environments

tl;dr: I write in quarto and do my work in both python and R. But lots of people still hate Python environments. I swear they are straightforward for this task now!

## Goals

- reproducible python/R environments
  - one-click launch in the cloud
  - consistent cross-platform local environments
- write in quarto markdown 
- include slides


## Install and Run

`pixi install`
`pixi run jupyter lab`

edit the notebooks as you like

## Execute and Build

`cd paper`
`pixi run quarto render`

will run the python and r noteooks and generate the html and pdf in `output/`

