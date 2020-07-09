# GIT REPOSITORY HOW-TO GUIDE

## git init/git clone

A *[git repository](https://git-scm.com/book/en/v2/Git-Basics-Getting-a-Git-Repository)* is a virtual storage of your project, allowing to save versions of your code and to access when needed.

## SETTING UP A REPOSITORY (Repo) UNDER THE GIT VERSION CONTROL

[How to set-up Git on your device](https://git-scm.com/book/en/v2/Getting-Started-First-Time-Git-Setup)

### Initializing a new repository

To create a new repo, you'll use the `git init` command. git init is a one-time command you use during the initial setup of a new repo. Executing this command will create a new **.git**   subdirectory in your current working directory. This will also create a new branch called master.

### Versioning an existing project with a new git repository

Assuming you already have a project directory and you would like to create a repo within it:

* First cd into root project directory.
* execute `git init`
This will as mentioned above create same **.git** subdirectory but scoped to that project dir.

### Cloning an existing repo

If a project has been set up in a central repository, the **clone** command is the most common way to obtain a local development clone.Once a developer(contributor) has obtained a working copy, all version control operations are managed through their local repository.

```console
$foo@bar git clone <repo url>
```  

 git clone creates a local clone of remote repo.

The URL can be found on this page under **CODE** dropdown can be found [on this page.](https://github.com/auvzhcet/Documentation)

### Saving changes to the repo

#### git add / git commit**

Once you have completed with cloning and and working on project

* Add changes to staging area

```console
$foo@bar git add <file names or the whole dir(./ )>
```  

* Commit those changes

```console
$foo@bar git commit -m "Message about the commit"
```

### Collaboration

#### git push

If *git clone* was used in initializing a new repository , then this repo is already configured for remote collaboration.
git clone  will automatically configure the repo with a remote pointed to the Git URL cloned it from. This means that once changes made to a file are committed, they  can be pushed using `git push` those changes to the remote repository.

If you prefer to host your own remote repo initialized with `git init`, you'll need to set up a "Bare Repository." Both `git init` and `git clone` accept a `--bare` argument. The most common use case for bare repo is to create a remote central Git repository.
