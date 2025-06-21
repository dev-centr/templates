# FoodTruckNerdz Workspace

## Dev machine setup
This repository holds files that provide a workspace that coordinates the other repositories, in VSCode. This repository is used to coordinate the other FTN repositories after downloading on your local machine.
Syncing this repository will not accidentally include the other repositories in this one. The .gitignore file has all repository names in it, to ensure this does not happen.
If you are adding a new repository to the workspace, be sure to add its folder name to the .gitignore here.

## Why?
For AI tooling. We put the VSCode .code-workspace file here separately so that you can use AI to change every project simultaneously when you need to make broad changes. If the workspace file were located in each repository, then RooCode plugin for VSCode would not have a way to work on all projects without reopening every project. More power to you.

## Instructions
Download this repository, then download the other repositories inside this repository's folder.
- FoodTruckNerdzSite
- food-truck-api
- ftn-site-vercel
