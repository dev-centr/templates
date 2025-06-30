# FoodTruckNerdz Workspace

_Development machine setup instructions._

## Why?

For AI tooling. The VSCode .code-workspace file is kept here separately
so you can use AI to change every project simultaneously when you need
to make broad changes. If the workspace file were located in each
repository, then RooCode plugin for VSCode would not have a way to work
on all projects without reopening every project. More power to you.

We also include a collection of good extensions to install for VSCode.
We have suggested plugins as well as some alternative options listed.

> [!Note]
> To see the alternative options and the full list of suggestions, open
> the `FoodTruckNerdz-Workspace.code-workspace` file and read the
> "extensions" section.

## Instructions

### 1. Fork on GitHub

To contribute, fork this repository to your own GitHub account using the
'Fork' button on GitHub.

### 2. Clone to your machine with git or GitHub Desktop

Clone your fork using GitHub Desktop or another version control system
(such as the `git` command line).

Download all the following repositories into this repository's folder on
your machine:

- food-truck-api
- ftn-site-vercel

Optional repositories if you want to look at some failed ideas or
compare to the remake:

- FoodTruckNerdzSite

This repository is used to coordinate the other repositories on your
local disk after cloning. It contains a .code-workspace file that
defines the other repositories and allows tools like RooCode to manage
the entire code-base as a single workspace. When changes need to be made
to multiple projects simultaneously, the AI can do it for you.

This repository is configured to exclude the other repositories using
`.gitignore`, so when you use `git push` to sync changes made in the
base folder, the other repositories are not included. The .gitignore
file has all repository names in it to ensure no projects are synced
into the base repository.

If git accidentally syncs a child repository to this one, add the child
repository or update its records in the [.gitignore](/.gitignore) file.
