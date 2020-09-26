# Table of contents

- [Creating a new manuscript](#creating-a-new-manuscript)
  * [Configuration](#configuration)
  * [Create repository](#create-repository)
  * [Continuous integration](#continuous-integration)
    + [GitHub Actions](#github-actions)
    + [SSH Deploy Key](#ssh-deploy-key)
      - [Add the public key to GitHub](#add-the-public-key-to-github)
      - [Add the private key to GitHub](#add-the-private-key-to-github)
    + [Travis CI](#travis-ci)
    + [Previewing pull request builds with AppVeyor](#previewing-pull-request-builds-with-appveyor)
  * [README updates](#readme-updates)
  * [Finalize](#finalize)
- [Merging upstream rootstock changes](#merging-upstream-rootstock-changes)

_generated with [markdown-toc](https://ecotrust-canada.github.io/markdown-toc/)_

# Creating a new manuscript

These instructions detail how to create a new manuscript based off of the [`lubianat/ideas_rootstock`](https://github.com/lubianat/ideas_rootstock), derived from the [`manubot/rootstock`](https://github.com/manubot/rootstock/) repository.

The process can be a bit challenging, because it requires a few steps that are difficult to automate.
However, you will only have to perform these steps once for each manuscript.

Many of the original steps were removed for simplicity. 

## Configuration

First, you must configure two environment variables (`OWNER` and `REPO`).
These variables specify the GitHub repository for the manuscript (i.e. `https://github.com/OWNER/REPO`).
Make sure that the case of `OWNER` matches how your username is displayed on GitHub.
In general, assume that all commands in this setup are case-sensitive.

**Edit the following commands with your manuscript's information:**

```sh
# GitHub username (change from manubot)
OWNER=manubot
# Repository name (change from rootstock)
REPO=rootstock
```

## Create repository

**Execute the remaining commands verbatim.**
They do not need to be edited (if the setup works as intended).

Next you must clone `lubianat/ideas_rootstock` and reconfigure the remote repositories:

```sh
# Clone lubianat/ideas_rootstock
git clone --single-branch https://github.com/lubianat/ideas_rootstock.git $REPO
cd $REPO

# Configure remotes
git remote add rootstock https://github.com/lubianat/ideas_rootstock.git

# Option A: Set origin URL using its web address
git remote set-url origin https://github.com/$OWNER/$REPO.git

# Option B: If GitHub SSH key access is not enabled for OWNER, run the following command instead
# git remote set-url origin git@github.com:$OWNER/$REPO.git
```

Next, you must create an empty GitHub repository. This can be done manually at <https://github.com/new>.
Make sure to use the same "Owner" and "Repository name" specified above.
Do not initialize the repository, other than optionally adding a Description.

Conversely, you can use GitHub for command line:
```sh
gh repo create
```
Next, push your cloned manuscript:

```sh
git push --set-upstream origin master
```

### GitHub Actions

GitHub Actions is the recommended default CI service because it requires no additional setup.

GitHub Actions is _usually_ able to deploy without any setup using the [`GITHUB_TOKEN`](https://help.github.com/en/actions/configuring-and-managing-workflows/authenticating-with-the-github_token) for authentication.
GitHub Pages deployment using `GITHUB_TOKEN` recently started working on GitHub without an official announcement.
If it does not work for you after completing this setup, try reselecting "gh-pages branch" as the Source for GitHub Pages in the repository Settings.
GitHub Pages should now trigger on the next commit.

## README updates

The continuous integration configuration should now be complete.
Now update `README.md` files to reference your new repository:

```shell
# Perform substitutions
sed "s/lubianat\/ideas_rootstock/$OWNER\/$REPO/g" README.md > tmp && mv -f tmp README.md
sed "s/lubianat\.github\.io\/ideas_rootstock/$OWNER\.github\.io\/$REPO/g" README.md > tmp && mv -f tmp README.md
```

## Finalize

The `content/02.delete-me.md` file details the Markdown syntax and formatting options available with Manubot.
Remove it to reduce the content to a blank manuscript:

```shell
# Remove deletable content file
git rm content/02.delete-me.md
```

Run `git status` or `git diff --color-words` to double check the changes thus far.
If the changes look okay, commit and push:

```shell
git add --update
git commit --message "Brand repo to $OWNER/$REPO"
git push origin master
```

You should be good to go now.
A good first step is to modify [`content/metadata.yaml`](content/metadata.yaml) with the relevant information for your manuscript.
It now contains my metadata as default. 
