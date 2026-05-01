---
title: 'Git Cheatsheets for Quick Reference'
---

## Git Cheatsheets for Quick Reference

Here is the cheat sheet created by Carpentry @ UCSB for this workshop. You can print or save it as a PDF directly from this page!

<button onclick="window.print()" class="print-button" style="margin-bottom: 20px; padding: 10px 15px; font-weight: bold; cursor: pointer;">🖨️ Print / Export Cheat Sheet to PDF</button>

::: {#printable-cheatsheet .printable-cheatsheet}

## Git Cheat Sheet

*Version control is like an unlimited ‘undo’. It allows many people to work in parallel, collaborate and share their work.*

### Setting Up Git - Once per computer
Configure user information for all local repositories:
```
$ git config --global user.name "[name]"
$ git config --global user.email "[email]"
$ git config --global init.defaultBranch main
```

### Creating a Repository
Git stores all of its repository data in the `.git` directory.

Turn an existing directory into a git repository:
```
$ git init
```

### Tracking Changes
Files can be stored in a project’s working directory (which users see), the staging area (where the next commit is being built up, after `git add`) and the local repository (where commits are permanently recorded, after `git commit`).

Show the status of a repository:
```
$ git status
```

Put files in the staging area:
```
$ git add [file]
```

Save staged content as a new commit in the local repository:
```
$ git commit -m "[descriptive message]"
```

### Exploring History
Display differences in file compared to a previous commit:
```
$ git diff [commit] [file]
```

Restore version of a file from last commit:
```
$ git restore [file]
```

Restore version of a file from a previous commit:
```
$ git restore --source [commit] [file]
```

### Ignoring Things
The `.gitignore` file is a text file that tells Git which files or folders to track and which to ignore in the repository.

### Remotes in GitHub / Collaborating
First, you’ll need to set up SSH to authenticate with GitHub. A local Git repository can be connected to one or more remote repositories in GitHub (or other hosting platforms).

Clone (download) a GitHub repository:
```
$ git clone [url]
```

Copy changes from a local repository to a remote repository:
```
$ git push
```

Copy changes from a remote repository to a local repository:
```
$ git pull
```

### Branches
Branches allow parallel work without affecting the main codebase. Each branch is a parallel snapshot until merged.

See current branches:
```
$ git branch
```

Switch to a different branch:
```
$ git switch [branch-name]
```

Create a new branch:
```
$ git switch -c [branch-name]
```

Merge a specified branch’s history into current branch:
```
$ git merge [branch]
```

Delete the specified branch:
```
$ git branch -d [branch-name]
```

*Pull requests (PR) on GitHub enable review and discussion before merging.*

### Forks
A fork is your own copy of another GitHub repository (the “upstream” repo). You can make changes freely even if you don’t have write access to the upstream repo.

To see current remote repositories being tracked:
```
$ git remote -v
```

Add a new remote being tracked, maybe the upstream repo:
```
$ git remote add [remote-name] [url]
```

You can contribute by creating a pull request from your fork to the upstream repository.

### Conflicts
Conflicts occur when two or more people change the same lines of the same file. Git highlights conflicts so that they can be resolved. Defining a workflow with your team is the first step to avoid them.

### Open Science / Licensing / Citation / Hosting
Open scientific work is more useful and accelerates discovery. The `LICENSE.md` file indicates how the contents of the repo may be used. Add a `CITATION` file to explain how you want your work cited.

![](../episodes/fig/git_staging.svg){style='max-width: 100%; display: block; margin: 0 auto;'}
<p style="text-align: center; font-size: 0.8em; margin-top: 5px !important;">Huang, Daisie (2015). How Git works: a cartoon.</p>

:::


<style>
/* Web layout (optional) */
.printable-cheatsheet {
  column-count: 2;
  column-gap: 30px;
  background-color: transparent;
  padding: 20px;
  border-radius: 8px;
  border: 1px solid var(--border-color, #ddd); /* Adapts slightly to dark mode if variable exists */
}
.printable-cheatsheet h2 {
  column-span: all;
  text-align: center;
  margin-top: 0;
}
.printable-cheatsheet h3 {
  margin-top: 1.5em;
  font-size: 1.1em;
  border-bottom: 1px solid var(--border-color, #ddd);
  break-after: avoid;
  page-break-after: avoid;
}
.printable-cheatsheet pre {
  padding: 8px !important;
  padding-top: 8px !important;
  border-radius: 4px;
  margin: 0 0 0.8em 0 !important;
  white-space: pre-wrap !important;
  overflow-wrap: break-word !important;
}
.printable-cheatsheet pre code {
  display: block !important; 
  margin-top: 0 !important;
  padding-top: 0 !important;
  line-height: 1.2 !important;
  margin: 0 !important;
  padding: 0 !important;
  white-space: pre-wrap !important;
  overflow-wrap: break-word !important;
}
.printable-cheatsheet p {
  font-size: 0.9em;
  margin: 0.5em 0 0.1em 0 !important;
}
.printable-cheatsheet pre .copy-button,
.printable-cheatsheet pre button {
  display: none !important;
}

/* Kill any invisible language badges or empty injected content */
.printable-cheatsheet pre::before,
.printable-cheatsheet code::before {
  content: none !important;
  display: none !important;
}

/* Print layout */
@media print {
  @page {
    margin: 0.5cm;
  }
  
  /* Hide everything in the body by default and lock to 1 page */
  html, body {
    height: 100vh;
    overflow: hidden;
    margin: 0;
    padding: 0;
  }
  
  body * {
    visibility: hidden;
  }
  
  /* Show only the cheat sheet wrapper and its children */
  #printable-cheatsheet, #printable-cheatsheet * {
    visibility: visible;
    color: black !important;
  }
  
  /* Reposition the cheat sheet to the top left of the printed page */
  #printable-cheatsheet {
    position: absolute;
    left: 0;
    top: 0;
    width: 100%;
    margin: 0;
    padding: 0;
    border: none;
    background-color: transparent;
    column-count: 2;
    column-gap: 30px;
  }

  #printable-cheatsheet h2 {
    font-size: 16pt;
    margin-bottom: 2px;
  }

  #printable-cheatsheet h3 {
    font-size: 12pt;
    margin-top: 3px;
    margin-bottom: 1px;
    padding-bottom: 0px;
  }
  #printable-cheatsheet p {
    font-size: 10pt;
    margin: 1px 0 0 0 !important;
    line-height: 1.2;
  }
  #printable-cheatsheet pre {
    font-size: 10pt;
    border: 1px solid #ccc;
    background-color: transparent !important;
    padding: 2px !important;
    margin: 0 0 3px 0 !important;
  }
  #printable-cheatsheet pre code {
    margin: 0 !important;
    padding: 0 !important;
  }
  
  /* Hide typical site headers/footers */
  .print-button, header, footer, nav, aside, .sidebar {
    display: none !important;
  }
}

@media screen and (max-width: 768px) {
  .printable-cheatsheet {
    column-count: 1;
  }
}
</style>

## Other resources

- Printable Git cheatsheets in several languages made by GitHub are [available here](https://github.github.com/training-kit/) ([English version](https://github.github.com/training-kit/downloads/github-git-cheat-sheet.pdf)). More material is available from the [GitHub training website](https://try.github.io/).
- Here is a great [refresher for Bash commands](https://eds-221-programming-essentials.github.io/course-materials/interactive-sessions/interactive-session-1a.html#commonly-used-and-very-helpful-bash-commands) from EDS 221 - Scientific Programming Essentials 
- An [interactive one-page visualisation](https://ndpsoftware.com/git-cheatsheet.html)
  about the relationships between workspace, staging area, local repository, upstream repository, and the commands associated with each (with explanations).
- Both resources are also available in other languages (e.g. Spanish, French, and more).
- "[Happy Git and GitHub for the useR](https://happygitwithr.com)" is an accessible, free online book by Jenny Bryan on how to setup and use Git and GitHub with specific references on the integration of Git with RStudio and working with Git in R.
- [Open Scientific Code using Git and GitHub](https://open-source-for-researchers.github.io/open-source-workshop/) - A collection of explanations and short practical exercises to help researchers learn more about version control and open source software.

## Glossary

[changeset]{#changeset}
:   A group of changes to one or more files that are or will be added
to a single [commit](#commit) in a [version control](#version-control)
[repository](#repository).

[commit]{#commit}
:   To record the current state of a set of files (a [changeset](#changeset))
in a [version control](#version-control) [repository](#repository). As a noun,
the result of committing, i.e. a recorded changeset in a repository.
If a commit contains changes to multiple files,
all of the changes are recorded together.

[conflict]{#conflict}
:   A change made by one user of a [version control system](#version-control)
that is incompatible with changes made by other users.
Helping users [resolve](#resolve) conflicts
is one of version control's major tasks.

[HTTP]{#http}
:   The Hypertext Transfer [Protocol](#protocol) used for sharing web pages and other data
on the World Wide Web.

[merge]{#merge}
:   (a repository): To reconcile two sets of changes to a
[repository](#repository).

[protocol]{#protocol}
:   A set of rules that define how one computer communicates with another.
Common protocols on the Internet include [HTTP](#http) and [SSH](#ssh).

[remote]{#remote}
:   (of a repository) A version control [repository](#repository) connected to another,
in such way that both can be kept in sync exchanging [commits](#commit).

[repository]{#repository}
:   A storage area where a [version control](#version-control) system
stores the full history of [commits](#commit) of a project and information
about who changed what, when.

[resolve]{#resolve}
:   To eliminate the [conflicts](#conflict) between two or more incompatible changes to a file or set of files
being managed by a [version control](#version-control) system.

[revision]{#revision}
:   A synonym for [commit](#commit).

[SHA-1]{#sha-1}
:   [SHA-1 hashes](https://en.wikipedia.org/wiki/SHA-1) is what Git uses to compute identifiers, including for commits.
To compute these, Git uses not only the actual change of a commit, but also its metadata (such as date, author,
message), including the identifiers of all commits of preceding changes. This makes Git commit IDs virtually unique.
I.e., the likelihood that two commits made independently, even of the same change, receive the same ID is exceedingly
small.

[SSH]{#ssh}
:   The Secure Shell [protocol](#protocol) used for secure communication between computers.

[timestamp]{#timestamp}
:   A record of when a particular event occurred.

[version control]{#version-control}
:   A tool for managing changes to a set of files.
Each set of changes creates a new [commit](#commit) of the files;
the version control system allows users to recover old commits reliably,
and helps manage conflicting changes made by different users.