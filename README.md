![Version](https://img.shields.io/static/v1?label=latexemacs30&message=0.2&color=brightcolor)
[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](https://opensource.org/licenses/MIT)


# LaTeX-dominated configuration for GNU Emacs Version 30

This repository stores the configuration file (init.el).
This configuration works with GNU Emacs Version 30.5, the bleeding edge development version.

I have mapped a bash alias to this profile and Emacs30 so that I can use it parallel with other Emacs profiles.

After you have tweaked this configuration to your liking, you can gain instant access to an Emacs session by running the Emacs demon in the background and using the emacsclient to open a new frame instantly.
The 2nd command starts an Emacs daemon using this configuration.
After the daemon is running, you can use the third alias to fire up the Emacs client for instant access.

The last command will stop the demon.
You have to stop the demon whenever you make a change to the configuration.
After the configuration change has been made, you can restart the demon with the new configuration.
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

I download the init.el file and attempted to install it from scratch.
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

## Update history

|Version      | Changes                                                                                                                                    | Date                 |
|:-----------:|:------------------------------------------------------------------------------------------------------------------------------------------:|:--------------------:|
| Version 0.2 |  Added funding and update table.                                                                                                             | 2024 May 4           |

## Funding

- NIH: R01 CA242845, R01 AI088011
- NIH: P30 CA225520 (PI: R. Mannel); P20GM103640 and P30GM145423 (PI: A. West)
