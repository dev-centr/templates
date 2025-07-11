# FoodTruckNerdz Developer Instructions

This is the base repository / master repository, inside which you should load all of the other repositories. This repository holds settings files and instructions for setting up your development workspace on your local machine.

![pic](/files/Repository%20Structure%20-%20Vercel%20Free.svg)

[Source Excalidraw file](/files/Repository%20Structure%20-%20Vercel%20Free.excalidraw)

1. First, clone this base repository to your machine with git or GitHub Desktop.
2. Then clone all other FTN repositories into the base repository.
3. Open the FoodTruckNerdz.code-workspace file in VSCode to set up VSCode.
4. If you are working on something that could break things, create a new branch in the repository, using git, GitHub, or VSCode.
5. If you are creating a new repository/project, add it to the exclusions list in the Base repository's [.gitignore](/.gitignore) file.

Once you are finished with your changes:

1. Commit changes to the clone.
2. Set up your local SSH key.
3. Sync your clone to the team's GitHub. (`git push`). Tip: Try to set up your SSH agent so you don't have to type your SSH key password every time you submit your changes (if it will cooperate--Windows's is finicky).

> [!NOTE]
> We do not encourage you to fork the repository to your personal GitHub account. It is not necessary. Just use branches. Forking a repository causes issues when you want to create a pull request. You have to wait for the existing PR to be approved before you can submit another PR. So in this way it is an annoyance to you.

<details>
<summary>Why not fork?</summary>

**It is generally NOT recommended to directly work on the `main` (or `master`) branch of your _fork_ and then create a Pull Request from it.**

Here's why, and what the better practice is:

**Why working on `main` of your fork is problematic:**

- **Single PR at a time:** If you work directly on `main` in your fork, you can only have _one active Pull Request_ open at a time for that specific fork. If you want to contribute another feature or bug fix while the first PR is still pending, you'll run into issues.
- **Conflicting commits:** Once your PR is merged into the upstream (original) repository's `main` branch, your fork's `main` branch now has those same commits. If you then try to pull the latest changes from the upstream `main` to update your fork's `main`, you'll likely face merge conflicts because those commits already exist in your history. It becomes a mess to synchronize.
- **Maintainer collaboration:** If maintainers of the original project need to make small changes or test things on your PR branch, it's difficult if you're on your `main` branch, especially if branch protection rules are in place.

**The recommended approach (which is what I meant by "work in a dedicated feature branch"):**

1. **Fork the repository:** This creates your own copy of the entire repository under your GitHub account.
2. **Clone your fork locally:** Get a local copy of your forked repository.
3. **Create a new, dedicated feature branch:** **This is the crucial step.** For every new feature, bug fix, or contribution, create a new branch from your fork's `main` branch (e.g., `git checkout -b my-new-feature`).
4. **Make your changes and commit them on this feature branch.**
5. **Push the feature branch to your fork:** `git push origin my-new-feature`.
6. **Open a Pull Request:** From your feature branch in your fork to the `main` branch of the _original_ (upstream) repository.

**Benefits of using feature branches in your fork:**

- **Multiple contributions:** You can work on multiple features or fixes simultaneously by creating separate branches for each.
- **Clean history:** Your `main` branch in your fork can always mirror the upstream `main` branch, making it easy to keep it updated without conflicts.
- **Easier collaboration:** Maintainers can easily push changes to your feature branch if you allow edits, streamlining the review process.
- **Isolation:** Changes in one feature branch don't affect other ongoing work.

So, to summarize: **Yes, forking a repo is a legitimate and often necessary first step.** But after forking, the best practice is to **create a new, separate branch for each set of changes you want to propose via a Pull Request**, rather than working directly on your fork's `main` branch.

</details>

## Why?

For easy onboarding and a consistent development environment for our team, as well as a single workspace for AI tooling to have access to the entire code-base at the same time. This allows you to make broad changes to the code base quickly.

A `.code-workspace` file containing settings and customizations for VSCode is provided. The file is stored in this repository, instead of the individual repositories, so that the repositories are kept clean and separate from the VSCode settings.

If the `.code-workspace` file were located in each repository, then AI plugins for VSCode would not have a way to work on all projects simultaneously.

We also provide a collection of suggested good extensions for VSCode in the `.code-workspace` file. You can see some alternatives by opening up the file and looking at the appropriate section.

> [!Note]
> To see the alternative options and the full list of suggestions, open `FoodTruckNerdz.code-workspace` in VSCode and read the "extensions" section.

## Details

- The `.code-workspace` file defines repositories and assigns them labels in VSCode.
- Git is configured to exclude the other repositories in the `.gitignore` file, so when you sync changes made in the child repositories, they do not get added to the Base accidentally. The .gitignore file contains all repository names in it to ensure this.

> [!WARNING]
> If git accidentally syncs a child repository to this one, exclude the repository by writing it in the [.gitignore](/.gitignore) file.

## Additional tools

### Web Dev

- [VisBug](https://chromewebstore.google.com/detail/visbug/cdockenadnadldjbbgcallicgledbeoc) - Lets you edit a web design in your browser using drag and drop while the page is live.
- [Jam.dev](https://jam.dev) - Debugging tool. Lets you record video of website problem as well as capturing technical logs and creates bug reports automatically.
