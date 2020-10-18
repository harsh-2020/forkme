

# forkme
This repo is a test repo for the SWC bootcamp to test forking, fetching, and pull requests. 

Fork and Pull Request Workflow
==============================

<!-- :: \iffalse -->
[![Download PDF][SHIELD_PDF]][DOWNLOAD_PDF]
[![Download TXT][SHIELD_TXT]][DOWNLOAD_TXT]
[![CC BY 4.0 License][SHIELD_CCBY]][CCBY]
<!-- :: -->
[SHIELD_PDF]: https://img.shields.io/badge/download-PDF-brightgreen.svg
[SHIELD_TXT]: https://img.shields.io/badge/download-TXT-brightgreen.svg
[SHIELD_CCBY]: https://img.shields.io/badge/license-CC%20BY%204.0-blue.svg
[DOWNLOAD_PDF]: https://github.com/susam/gitpr/releases/download/0.6.0/gitpr.pdf
[DOWNLOAD_TXT]: https://github.com/susam/gitpr/releases/download/0.6.0/gitpr.txt
<!-- :: \fi -->
<!-- Version 0.6.0 (2018-11-19) -->
<!-- :: \maketitle -->

Introduction
------------

Every project has a main development branch where the developers push
commits on a day-to-day basis. Usually, the main development branch is
`master` but some projects choose to have `develop` or `trunk` or
another branch for day-to-day development activities. We refer to this
main development branch as the *main development branch* throughout this
document to keep the text general. However in the command examples and
ASCII-diagrams, we use `master` as an example of the main development
branch.

We use the following placeholders in the command examples and
ASCII-diagrams in this document:

  - `GITHUB`: [`github.com`](https://github.com/) or domain
    name/hostname of your private GitHub Enterprise system.
  - `USER` or `CONTRIBUTOR`: The user that forks an upstream repository,
    creates pull requests, and sends them to the upstream repository.
  - `UPSTREAM-OWNER`: Owner of the upstream repository. This is the name
    of the user or organization that merges pull requests into the
    upstream repository.
  - `REPO`: Repository name.
  - `FILES`: One or more filenames to be staged for a commit.
  - `TOPIC-BRANCH`: Feature-specific or bug-specific branch where a
    contributor develops her or his contribution. This is referred to as
    the *topic branch* in the text.
    
    Create Pull Request
-------------------

This section is meant for developers who contribute new commits to the
upstream repository from their personal fork.


### Fork and Clone

On GitHub, fork the upstream repository to your personal user account.

Then clone your fork from your personal GitHub user account to your
local system and set the upstream repository URL as a remote named
`upstream`.

    git clone https://GITHUB/USER/REPO.git
    cd REPO
    git remote add upstream https://GITHUB/UPSTREAM-OWNER/REPO.git
    git remote -v

Now the remote named `upstream` points to the upstream repository and
the remote named `origin` points to your fork.


### Work on Pull Request

Work on a new pull request in a new topic branch and commit it to your
fork. Remember to use a meaningful name instead of `TOPIC-BRANCH` in the
commands below.

    git checkout -b TOPIC-BRANCH
    git add FILES
    git commit
    git push origin TOPIC-BRANCH

Create pull request via GitHub web interface as per the following steps:

  - Go to your fork on GitHub.
  - Switch to the topic branch.
  - Click *Compare & pull request*.
  - Click *Create pull request*.

Wait for an upstream developer to review and merge your pull request.

If there are review comments to be addressed, continue working on your
branch, commiting, optionally rebasing, amending, squashing, and
dropping them, and pushing them to the topic branch of `origin` (your
fork). Any changes to the topic branch automatically become available in
the pull request.

In the fork and pull request workflow, a contributor should never commit
anything to the main development branch of personal fork. This makes it
very easy to keep the main development branch of your fork in sync with
that of the upstream repository. This is explained in the next
subsection.

<!-- :: \pagebreak -->
