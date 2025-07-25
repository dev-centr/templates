# FoodTruckNerdz Developer Instructions

This is the Base repository. It holds instructions and support files for setting up your local machine and committing code.

## Setup

Set up this repository first, then put the other repositories inside of it. This repository coordinates the other repositories so that AI tools can be used to make broad changes quickly across all FTN projects when needed. After downloading all of the repositories, launch the workspace by opening the [`FoodTruckNerdz.code-workspace`](<FoodTruckNerdz.code-workspace>) file in VSCode. The settings specified in it will apply for all projects in the workspace.

### Steps:

1. Clone this repository to your machine.
2. Clone all other repositories that you will be working on into the base repository.
3. Open the `FoodTruckNerdz.code-workspace` file in VSCode. If you are editing the file, look for a button in the editor that says "open this workspace".

> [!Warning]
> If your repositories are set up incorrectly, the files will not show up, but the root nodes' labels will.

> [!Important]
> - Create a new code branch in repositories before you start editing, if you are working on something that could break things.
> - If you create a new repository/project, register it to the [`.gitignore`](<.gitignore>)'s exclusions list in the base repository.

## Committing

Once you are ready to commit your code:

1. Make multiple small commits and be descriptive about your changes. Commit them in small batches by picking a few related files to add to each commit. You can make several commits locally and then push/sync the changes up to GitHub all at once. VSCode has a 'sync' button that attempts to `pull` then `push` code. If the pull conflicts with your code, you will have to resolve the conflict in the merge editor. The merge editor is not the same as the diff viewer.
2. Sync your changes to the GitHub. In order to submit code, you must [set up your local SSH key](<https://github.com/FoodTruckNerds/docs/blob/3a503a52af0bb5c354bd4ac0519543a62576cc28/plain%20markdown/ssh-keys-setup.md>) first.
    - **Warning: VSCode SSH Key Path Bug:** If you are using VSCode and experiencing repeated password prompts for repositories synced with SSH URLs, ensure your local SSH key file is *not* located in a path that contains spaces. VSCode currently has a bug that prevents it from correctly reading SSH keys from paths with spaces, leading to continuous password requests. For more details, refer to the bug report: <https://github.com/microsoft/vscode/issues/203128>. If this is not the problem, make sure your git credential helper is set. Use `git config credential.helper` to check if it is set. It should have been set at the system level for you when you installed git. If it is broken, set it either locally (repo), globally (user), or system-wide (OS) with the following in Windows, macOS, or Linux:
      - `git config --local credential.helper manager`
      - `git config --global credential.helper manager`
      - `git config --system credential.helper manager` as Admin

      or if it is not already installed on macOS:
      - `brew install --cask git-credential-manager`
     
      You can check what level(s) are configured and where to find the settings files using `git config --show-origin credential.helper`. Please note there are no examples on the internet using this, but this is the correct solution. The official git-config [documentation](<https://git-scm.com/docs/git-config>) does not specifically mention this, but the functionality is implied.

      For a full in-depth explanation of config levels, see this article: [System , global, and local Git config files on Windows and Linux](<https://www.theserverside.com/blog/Coffee-Talk-Java-News-Stories-and-Opinions/Where-system-global-and-local-Windows-Git-config-files-are-saved>)

> [!Note]
> We do not encourage you to fork the repository to your personal GitHub account. It is not necessary. Just use branches. Forking a repository causes issues when you want to create a pull request. You have to wait for the existing PR to be approved before you can submit another PR. So in this way it is an annoyance to you.
>
> <details>
> <summary>Why not to fork</summary>
>
> It is generally NOT recommended to directly work on the `main` (or `master`) branch of your _fork_ and then create a Pull Request from it.
>
> Here's why, and what the better practice is:
>
> **Why working on `main` of your fork is problematic:**
>
> - **Single PR at a time:** If you work directly on `main` in your fork, you can only have _one active Pull Request_ open at a time for that specific fork. If you want to contribute another feature or bug fix while the first PR is still pending, you'll run into issues.
> - **Conflicting commits:** Once your PR is merged into the upstream (original) repository's `main` branch, your fork's `main` branch now has those same commits. If you then try to pull the latest changes from the upstream `main` to update your fork's `main`, you'll likely face merge conflicts because those commits already exist in your history. It becomes a mess to synchronize.
> - **Maintainer collaboration:** If maintainers of the original project need to make small changes or test things on your PR branch, it's difficult if you're on your `main` branch, especially if branch protection rules are in place.
>
> **The recommended approach (which is what I meant by "work in a dedicated feature branch"):**
>
> 1. **Fork the repository:** This creates your own copy of the entire repository under your GitHub account.
> 2. **Clone your fork locally:** Get a local copy of your forked repository.
> 3. **Create a new, dedicated feature branch:** **This is the crucial step.** For every new feature, bug fix, or contribution, create a new branch from your fork's `main` branch (e.g., `git checkout -b my-new-feature`).
> 4. **Make your changes and commit them on this feature branch.**
> 5. **Push the feature branch to your fork:** `git push origin my-new-feature`.
> 6. **Open a Pull Request:** From your feature branch in your fork to the `main` branch of the _original_ (upstream) repository.
>
> **Benefits of using feature branches in your fork:**
>
> - **Multiple contributions:** You can work on multiple features or fixes simultaneously by creating separate branches for each.
> - **Clean history:** Your `main` branch in your fork can always mirror the upstream `main` branch, making it easy to keep it updated without conflicts.
> - **Easier collaboration:** Maintainers can easily push changes to your feature branch if you allow edits, streamlining the review process.
> - **Isolation:** Changes in one feature branch don't affect other ongoing work.
>
> So, to summarize: **Yes, forking a repo is a legitimate and often necessary first step.** But after forking, the best practice is to **create a new, separate branch for each set of changes you want to propose via a Pull Request**, rather than working directly on your fork's `main` branch.
>
> </details>

To get started on the Next.js web app, see `ftn-site-vercel`'s [`README.md`](<https://www.github.com/FoodTruckNerds/ftn-site-vercel/README.md>).

## Why?

- The `FoodTruckNerdz.code-workspace` file is stored here, instead of in the individual projects, so that the project repositories are kept clean and separate from the VSCode settings.
- If we provided `.code-workspace` files on a per-project basis, then AI plugins for VSCode would not have a way to work on all projects simultaneously.

## Details

- The [`FoodTruckNerdz.code-workspace`](<FoodTruckNerdz.code-workspace>) file configures VSCode to display labels for the different repositories.
- Git is configured to exclude the other repositories in the `.gitignore` file, so when you sync changes made in the child repositories, they do not get added to the Base accidentally. The .gitignore file contains all repository names in it to ensure this.
- We provide a list of suggested plugins in the "extensions" section in [`FoodTruckNerdz.code-workspace`](<FoodTruckNerdz.code-workspace>).

> [!Warning]
> If you accidentally sync a child repository to this one, add the repository to the [`.gitignore`](/.gitignore) file to prevent it from syncing in the future, commit that to the repository, and then use source control or a git GUI to "cherry pick" the commit that was _before_ accidentally committing, and merge it with the latest commit.
