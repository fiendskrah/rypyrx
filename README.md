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

(not strictly necessary, but its better to launch jlab from inside the notebooks dir)

`cd notebooks`
`pixi run jupyter lab`

if running in a codespace this starts a jupyter server on the VM's 'localhost'.
Open an existing notebook (or start a new one). When selecting a kernel, choose
'Existing jupyter server' and put in 127.0.0.1 as the host

edit the notebooks as you like

## Execute and Build

`cd paper`
`pixi run quarto render`

will run the python and r noteooks and generate the html and pdf in `output/`

