# Guidance for using git version control with Veda 2/TIMES

## Background
Git is a version control system. The term "repository" or "repo" refers to a working directory which is tracked by git. A git repo can be used collaboratively by means of creating a remote repo, which all contributors have access to.

A directory needs to be initialised as a git repo. When this is done, it creates a hidden ".git" folder that contains all the snapshots ("commits") of the repos history.

To save something to the history is a two-stage process: The change needs to be added to a staging area, and then committed. Several files can be added and committed in a single commit.

Git allows for different versions to exist in parallel, by the creation of branches. To combine these changes, branches need to be merged.


## Git and TIMES/Veda
Git is ideal for code and scripts. Veda is an executable that changes text files when it is used. This calls for the normal git workflows to be modified so that Git will not track every change. This is done by inclusion of a file that tells git to ignore certain files from the repo, and the user not stashing unneeded changes. The workflows in section 03 and 04 for not committing changes differs (committing to a temporary branch and stashing the changes respectively). Both methods work, and users can decide on their prefered option. 

This guide is not intended as an extensive introduction to git. An excellent resource for learning Git can be found [here](https://www.atlassian.com/git/tutorials).

## This guide
The files in this repository contain guidance for a git workflow used in TIMES model development with Veda 2. It uses the files of the demos_01 model as an example with the files copied to a new folder called demos_01_git.

Figures for each of the sections are contained in the "figures" folder.

The guidance is written to be used with Git Bash on a local machine running Windows and [GitHub] (https://github.com/) as the remote repository. The steps in the workflow will work for other operating systems and git interfaces and remote repository locations., but the methods of implementation will differ (terminal instead of Git Bash on Linux and Mac, or via a Gui)

The steps in the workflow are only a guide, and can be adapted as needed.


