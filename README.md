# FoodTruckNerdz Developer Instructions

This repository holds settings files and instructions for setting up
your development workspace on your local machine.

We require you to fork your repository to work on the code.

1. First, fork this repository to your personal GitHub account.
2. Then Clone your forked repository.
3. Then fork all other FTN repositories to your GitHub.
4. Then clone all forked FTN repositories into the local folder.
5. Open the FoodTruckNerdz.code-workspace file in VSCode to set up
   VSCode.

Once you are finished with your changes:

1. Commit changes to your cloned local repository.
2. Sync your changes to your personal GitHub. (`git push`)
3. Submit your personal GitHub version to the team's GitHub. Do this
   by submitting a "Pull Request".

## Why?

For easy onboarding and a consistent development environment for
our team, as well as a single workspace for AI tooling to have
access to the entire code-base at the same time. This allows you to
make broad changes to the code base quickly.

A `.code-workspace` file containing settings and customizations for
VSCode is provided. The file is stored in this repository, instead of
the individual repositories, so that the repositories are kept clean
and separate from the VSCode settings.

If the `.code-workspace` file were located in each repository, then
AI plugins for VSCode would not have a way to work on all projects
simultaneously.

We also provide a collection of suggested good extensions for VSCode in
the `.code-workspace` file. You can see some alternatives by opening up
the file and looking at the appropriate section.

> [!Note]
> To see the alternative options and the full list of suggestions, open
> `FoodTruckNerdz.code-workspace` in VSCode and read the "extensions"
> section.

## Details

- The `.code-workspace` file defines repositories and assigns them labels
  in VSCode.
- Git is configured to exclude the other repositories in the `.gitignore`
  file, so when you sync changes made in the child repositories, they do
  not get added to the Base accidentally. The .gitignore file contains all
  repository names in it to ensure this.

> [!WARNING]
> If git accidentally syncs a child repository to this one, add the
> repository to the [.gitignore](/.gitignore) file.
