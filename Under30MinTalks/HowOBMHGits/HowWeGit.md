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