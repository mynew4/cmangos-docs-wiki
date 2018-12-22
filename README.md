# Welcome to cmangos-docs

This repository is cloned from `https://github.com/cmangos/issues.wiki.git`, which can be viewed under this address: https://github.com/cmangos/issues/wiki

It serves as a place to create issues about the documentation, see the file system hierarchy, and an interface for developers to take a closer look at the history and branches.

If you want to edit the Wiki you can either create pull requests against this repository or just go to the [original Wiki](https://github.com/cmangos/issues/wiki) and edit it directly using the Github web interface (any Github user can edit it). This repository will pull changes made on the official wiki into its master branch.

**The wiki page on this repository is used for testing purposes and may not reflect the actual state of the original wiki!**

## Setting up the repository

**NOTE:** This is a preliminary workflow and subject to sudden changes.

To begin, clone the original wiki repository and change to the new directory:

```bash
git clone https://github.com/cmangos/issues.wiki.git
cd issues.wiki/
```

Add this repository and its wiki as remotes:

```bash
git remote add levi_repo https://github.com/Levitanious/cmangos-docs.git
git remote add levi_wiki https://github.com/Levitanious/cmangos-docs.wiki.git
```

When you use the `git remote -v` command, you should see the following output:

```bash
$ git remote -v
levi_repo       https://github.com/Levitanious/cmangos-docs.git (fetch)
levi_repo       https://github.com/Levitanious/cmangos-docs.git (push)
levi_wiki       https://github.com/Levitanious/cmangos-docs.wiki.git (fetch)
levi_wiki       https://github.com/Levitanious/cmangos-docs.wiki.git (push)
origin          https://github.com/cmangos/issues.wiki.git (fetch)
origin          https://github.com/cmangos/issues.wiki.git (push)
```
## Working with the repository

**NOTE:** This is a preliminary workflow and subject to sudden changes.

When you do not have push access, just create a branch on your fork and then open a pull request against it. Alternatively you can use the [original Wikis](https://github.com/cmangos/issues/wiki) web interface to edit it directly. Changes there will be pulled to this repository.

When you have push access, you can push to the master branch directly. Create your changes on a branch. Then make sure the `master` branch is still up-to-date with the original wiki:

```bash
git pull
```

Then merge your branch. Afterwards every change should be pushed to this repo and the original wiki:

```bash
git push
git push levi_repo
```
