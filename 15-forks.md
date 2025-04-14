---
title: Forks
teaching: 15
exercises: 0
---

::::::::::::::::::::::::::::::::::::::: objectives

- Explain what forks are and how they could be used.
- Learn how to submit a pull request from your fork.
- Show how to fetch changes from an upstream repo.

::::::::::::::::::::::::::::::::::::::::::::::::::

:::::::::::::::::::::::::::::::::::::::: questions

- How can I contribute to projects where I don't have permissions to push changes directly?

::::::::::::::::::::::::::::::::::::::::::::::::::

Until now, we've had permissions in the Owner's GitHub repository to push changes directly
on the 'main' branch (as covered on Episode 11. Collaborating), or to push a new branch (as covered on Episode 12. Branches).

We have yet to cover a case where we don't have those permissions, i.e. where we only have "read
access" to a public GitHub repository. This can be the case of a project with a big number of potential collaborators
where it's risky to give write access to everyone. For example, an open-source project
that could have dozens or hundreds of collaborators that the project owners don't know personally.

In that case, we'd use a [Fork](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/working-with-forks/about-forks)
, which is a personal copy of the original or 'upstream' repository. In this personal copy
you can make any changes you want, as it's a repo you "own" (always read the license on how you 
can use other people's work). You can make pull requests to the upstream repo with your changes,
or you can also pull changes made upstream to have your personal repo updated.

## 1. Contributing from your personal copy/fork

Now you'll contribute your own recipe (or a modification to an existing one) 
to the UCSBCarpentry cookbook! For this, you'll
fork the UCSBCarpentry/recipes-template repo [https://github.com/UCSBCarpentry/recipes-template](https://github.com/UCSBCarpentry/recipes-template),
add your recipe, and the open a pull request. There's only one new concept introduced here, forking,
but all other necessary commands and actions you have already learned.

To start, go the recipes-template repo, and click on the 'Fork' button at the upper-right corner.
In the page that loads after that, for the Repository name use 'recipes-fork-yourname',
changing _yournane_ with your actual name, don't change the defaults for the other options, 
and create the fork.

Clone the fork of the repo to your machine.

```bash
$ git clone git@github.com:yourname/recipes-fork-yourname.git ~/Desktop/recipes-fork-yourname
```

As you get ready to add your recipe or modify an existing one, create a new branch,
and give it a name that relates to your contribution.

```bash
$ git switch -c my-branch-yourname
```

After you've made the changes you wanted, stage, commit and push your changes.

```bash
$ git commit -a -m "Added my new recipe"
$ git push origin my-branch-yourname
```

Now on the GitHub page of the fork, you'll see you can submit a pull request just like
in the previous episode. Go ahead and do that, adding a title and a description to
your pull request.

Now the owner of the upstream repo, UCSBCarpentry, can see, review, modify, and merge
your suggested changes to the cookbook of recipes.


## 2. Fetching changes from the upstream repo

You can also keep in sync your personal fork with the original repo. If you use
the `git remote` command, you'll see that it only fetches and pushes changes to
your personal fork.

```bash
$ git remote -v
```
```output
origin  git@github.com:yourname/recipes-fork-yourname.git (fetch)
origin  git@github.com:yourname/recipes-fork-yourname.git (push)
```

But you can add a new remote that points to the original/upstream repo. For convenience,
we'll call this new remote 'upstream'. We can see that we now have an upstream remote
where we can fetch changes. However, we won't be able to push directly to it,
as we don't have the write permissions for that repo. To propose changes we'll have to
do it as we covered in the previous section.


```bash
$ git remote add upstream git@github.com:UCSBCarpentry/recipes-template.git
$ git remote -v
```
```output
origin  git@github.com:yourname/recipes-fork-yourname.git (fetch)
origin  git@github.com:yourname/recipes-fork-yourname.git (push)
upstream        git@github.com:UCSBCarpentry/recipes-template.git (fetch)
upstream        git@github.com:UCSBCarpentry/recipes-template.git (push)
```

::::::::::::::::::::::::::::::::::::: instructor

Here the instructor should make a change to the upstream repo, so learners
can pull those changes with their local repo and see how that happens.

:::::::::::::::::::::::::::::::::::::::::::::::::


After configuring your upstream remote, you can pull changes made in there to your
personal local repo with git pull. Notice here we are specifying 'main', as in that
branch is where we want to merge the upstream changes.

```bash
$ git pull upstream main
```

:::::::::::::::::::::::::::::::::::::::: keypoints

- A fork is your own copy of another GitHub repository (the "upstream" repo), stored under your account. You can make changes freely even if you don’t have write access to the original.

- You can contribute by creating a pull request from your fork to the upstream repository.

- To keep your fork updated, add the upstream repo as a remote with `git remote add` and pull changes with `git pull`.

- Forking is the standard way to contribute when you don’t have write access to a repo — it enables safe collaboration by letting you propose changes without affecting the original project directly.

::::::::::::::::::::::::::::::::::::::::::::::::::
