---
title: "How We Git"
theme: "moon"
transition: "concave"
enableMenu: false
enableChalkboard: false
enableTitleFooter: false
enableZoom: false
enableSearch: false
---

# How we Git

<img src="https://upload.wikimedia.org/wikipedia/commons/thumb/3/3f/Git_icon.svg/768px-Git_icon.svg.png" height="300" />

### A somewhat quick run through of BI development

---

## What

note:
According to wikipedia; git is a distributed version control system, which means the entire codebase and history of changes is downloaded onto the local machine.<br>
As opposed to TFS which is a centralised version control system, where technically nothing is downloaded locally.<br>
A master is stored in a repository denoted `ORIGIN`<br>

--

## Why

note:
Most popular version controlling system<br>
Free, Open Source, Universal; unlike TFS again which is locked down to Microsoft/Azure DevOps

--

## What we going to do

- Grab a code base from repository
- Create a new feature branch
- Make some changes to code
- Finish the feature branch; merge back to develop branch
- Create a release candidate, and release new version

---

## Before We Start

- All code will be put up on my personal git
https://github.com/niknudge/pres

- This will also be put up on Azure DevOps
- This is a surface look at our development process, at just git _(and some cross over with SQL Clone & SQL Source Control)_
- You can also return to this presentation [link tbc...]

---

# Getting the Repo

<img src="res/AccessCloneRepo.gif" width="80%">

note:
For Azure DevOps, we can access the repo URL from the website<br>
Just select the project you would like, use the bar on the left and<br>
open up the orange menu item. When the page has loaded you can select<br>
clone in the top left and you're given a URL to copy. [Video file can be<br>
found at](res/AccessCloneRepo.mp4)

---

# Downloading Repo

## Visual Studio

![Visual Studio Clone](res/VSClone.png)

--

# Downloading Repo

## CLI

```powershell
> git clone https://OxfordHealthBI@dev.azure.com/OxfordHealthBI/OxfordHealthDW/_git/OxfordHealthDW
```

--

# Downloading Repo

## SourceTree

![SourceTree Clone](res/STClone.png)

--

# Downloading Repo

## What We've Done

note:
So what we've done is download the master codebase as well as the metadata behind what changes have <br>
occurred and what changes are contained in other branches, which brings us to

---

# Branches

![Branch Status](res/BranchStatus.png)

note:
Branches are different states of the same codebase, we use the master branch to reflect the state of production<br>
In this example we see that the release branch is 27 commits ahead. In the backend these two codebases are very<br>
similar, the only difference is that the release branch contains a list of what rows have changed to what.

--

# Branching Stategies

We follow a method of branching named **"Gitflow"**, based on an initial [blog post by nvie](https://nvie.com/posts/a-successful-git-branching-model/)

Which recommends 2 permanent branches; `master` and `develop` that reflect a production state and development state respectively

--

# Gitflow

![Gitflow Diagram](https://www.nicepng.com/png/detail/321-3210678_release-branches-git-flow.png)

note:
Any new develop occurs in feature/ branches, this keeps any in progress development away from the current development<br>
state. When development is complete, the code is merged back into develop

--

# Gitflow

- New development occurs in `feature/` merged back into `develop`
- `release/` branched from develop, merged into `master` and back into `develop`

--

# Gitflow Tools

Gitflow is so popular that it has its own plugin for `git`. This allows you to simplify each of the common steps that occur in day to day development.

```powershell
> git flow feature start  <featurename>
> git flow feature finish <featurename>
```

--

# Gitflow Tools

Gitflow is also built into many other tools

<img src="res/VSgitflow.png" width="30%" /> <img src="res/STgitflow.png" width="30%" />

When we first clone a repository, we need to initiate with gitflow, the GUI tools prompt you to do this

note:
for example there are buttons in SourceTree and Visual Studio that utilises gitflow in the GUI

---

---

---

# How we don't do it

## Branching stategies

Whilst `gitflow` is popular, it's by no means perfect:

- Top level view can be confusing
- Easy to drift away from master branch
- Plugin makes it difficult/impossible to follow other git "best practices"

[Many articles](https://medium.com/@patrickporto/4-branching-workflows-for-git-30d0aaee7bf) discuss the pros and cons of other stategies used commonly

--

## Inbuilt git features

