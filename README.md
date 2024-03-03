# LaTeX-dominated configuration for GNU Emacs Version 30

This repository stores the configuration file (init.el).
This configuration works with GNU Emacs Version 30.5, the bleeding edge development version.

I have mapped a bash alias to this profile and Emacs30 so that I can use it parallel with other Emacs profiles.

```bash
e30ld='/Applications/Emacs30.5.0.app/Contents/MacOS/Emacs --init-directory ~/latex-emacs30 --debug-init'
```

I clone this distribution to the folder latex-emacs30 in my home directory.
Adjust the path to the Emacs binary as required.
This configuration should work on all operating systems with little need for adjustment.

## Testing on March 2, 2024

I download the init.el file and attempted to install from scratch.
Nine packages gave me errors about not being able to find the autoload files.
Fix this issue by copying the following nine commands into the scratch buffer and entering `C-x e` with the cursor at the end of each line.

```bash
(package-generate-autoloads "dash" "/Users/blaine/latex-emacs30-1/elpa/dash-20240103.1301/")
(package-generate-autoloads "biblio-core" "/Users/blaine/latex-emacs30-1/elpa/biblio-core-20230202.1721/")
(package-generate-autoloads "biblio" "/Users/blaine/latex-emacs30-1/elpa/biblio-20230202.1721/")
(package-generate-autoloads "websocket" "/Users/blaine/latex-emacs30-1/elpa/websocket-20230809.305/")
(package-generate-autoloads "avy" "/Users/blaine/latex-emacs30-1/elpa/avy-20230420.404/")
(package-generate-autoloads "electric-spacing" "/Users/blaine/latex-emacs30-1/elpa/electric-spacing-20220220.1540/")
(package-generate-autoloads "languagetool" "/Users/blaine/latex-emacs30-1/elpa/languagetool-20230325.507/")
(package-generate-autoloads "ef-themes" "/Users/blaine/latex-emacs30-1/elpa/ef-themes-1.5.1/")
(package-generate-autoloads "rainbow-delimiters" "/Users/blaine/latex-emacs30-1/elpa/rainbow-delimiters-20210515.1254/")
```
