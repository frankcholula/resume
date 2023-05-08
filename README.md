# Resume
Hello, hello, Frank here. You can find the raw `.tex` file and `.pdf` version of my resume below.
If you prefer my more detailed resume, see my notion site [here](https://frankcholula.notion.site/).

## Context
This resume uses the [forked version](https://github.com/NicolasOmar/AltaCV) of the [AltaCV](https://github.com/liantze/AltaCV) template by Nicolás Omar González Passerino(nicolas.passerino@gmail.com). I tweaked the colour palette and layout to my own taste.

Also Your boy is sick of re-writing `.tex` file on [`Overleaf`](https://overleaf.com) due to the slow compilation time and the installation process for `LaTeX` is awful. 
I tried to use [latex-docker](https://github.com/xu-cheng/latex-docker) image for compilation but it doesn't allow me to install the [LaTeX Workshop](https://marketplace.visualstudio.com/items?itemName=James-Yu.latex-workshop) extension in the dev container. I also tried out the `latex-workshop.docker.enabled` feature provided by `LaTeX Workshop` but because it spawns a docker container everytime you re-compile, it's also very slow.

This repo will have the tools necessary for local compilation.

## Setup
First, sync your [`Overleaf`](https://overleaf.com) files with the `Github` feature on their website.

I am using VS code's [development container feature](https://code.visualstudio.com/docs/devcontainers/containers) and I referenced the [`mrchoke/texlive`](https://hub.docker.com/r/mrchoke/texlive) image in my `devcontainer.json`.
Here's my user settings for `latex-workshop`, you can configure yours by pressing `cmd + shift + p` and search for `user settings`.
```json
{
    // latex-workshop
    "latex-workshop.latex.outDir": "./.out",
    "latex-workshop.view.pdf.viewer": "tab",
    "latex-workshop.synctex.afterBuild.enabled": true,
}

Press `cmd+shift+p` again and search `reopen in container` and voilà!
```

## Github Actions
I still have to implement [latex-action](https://github.com/xu-cheng/latex-action) so there will be auto-compilation upon releases.
