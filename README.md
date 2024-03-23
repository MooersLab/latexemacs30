![Version](https://img.shields.io/static/v1?label=latexemacs30&message=0.1&color=brightcolor)
[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](https://opensource.org/licenses/MIT)


# LaTeX-dominated configuration for GNU Emacs Version 30

This repository stores the configuration file (init.el).
This configuration works with GNU Emacs Version 30.5, the bleeding edge development version.

I have mapped a bash alias to this profile and Emacs30 so that I can use it parallel with other Emacs profiles.

After you have tweaked this configuration to your liking, you can gain instant access to an Emacs session by running the Emacs demon in the background and using the emacsclient to instantly open a new frame.
The 2nd command start a Emacs demon using this configuration.
After the demon is running, you can fire up the Emacs client for instant access by using the third alias.

The last command will stop the demon.
You have to stop the demon whenever you make a change to the configuration.
After the change to the configuration has been made, you can then restart the demon with the new configuration.
Because these are extra steps, it is best not to use a demon until your configuration has stabilized.

```bash
alias e30l1='/Applications/Emacs30.app/Contents/MacOS/Emacs --init-directory ~/latex-emacs30-1 --debug-init'

alias edml1='e30l1 --daemon'
alias ec30l1='emacsclient --alternate-editor="" -c &'

alias ec30k='emacsclient -e "(kill-emacs)"'
```

I clone this distribution to the folder latex-emacs30-1 in my home directory.
Adjust the path to the Emacs binary as required.
This configuration should work on all operating systems with little need for adjustment.

## Testing on March 2, 2024

I download the init.el file and attempted to install from scratch.
I used the same Eamcs30.0.5 build as before.
Nine packages gave me errors about not being able to find the autoload files.
I fixed this issue by copying the following nine commands into the scratch buffer and entering `C-x e` with the cursor at the end of each line.

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
