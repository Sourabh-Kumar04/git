# Git 
## Index
1. [Git and GIthub](#git-and-github)
    a. [Git and GIthub are different](#git-and-github-are-different)
    b. [Version Control System](#version-control-system)
    c. [Before Git](#before-git)
    d. [Installing git](#installing-git)
        1. [For Windows](#for-windows)
        2. [For MacOS(using homebrew)](#for-macos-using-homebrew)
        3. [For Linux](#for-linux)
        4. [GUI](#download-git-using-gui)
    e. [Account Github](#github-account)
2. [Terminology](#terminoly)
3. [Git Internals (Git behind the scene)](#git-behind-the-scene-git-internals)
4. [Branches in git](#branches-in-git)
5. [diff, stash, and Tags](#diff-stash-and-tags)
6. [Rebase and reflog](#rebase-and-reflog)
7. [Getting started with Github](#getting-started-with-github)


## Git and Github

### Git and Github are different
**Git**
- Git is a version control system that is used to track changes to your files.
- It is free and open-source software that is available for Linux, Windows and macOS.
- Since git is a software it can be installed on any computer.

**Github**
- Github is a web-based hosting service for Git repositories.
- Github is an online platform that allow you to store and share your code with others.
- Github is the popular provider of Git repositories.

### Version Control System
Version control systems are used to manage the history of your code. They allow you to track changes to your files and to collaborate with others.

Version control systems are essential for the software development. You can go back to previous code at any time.

### Before Git
Before Git became mainstream, version control systems were used by developers to manage their code. They were called **SCCS (Source Code Control System)**

SCCS was a propriety software that was used to manage the history of code. It was expensive and not user-freindly. 

Git was created to replace SCCS and to make version control more accessible and user-friendly.

Some common version control systems are 
- Subversion(SVN)
- CVS
- Perforce
- Mercury


### Installing GIt
To download and install Git using the terminal, follow these steps:

###### **For Windows:**

Open the Command Prompt: Press the Windows key + R to open the Run dialog box, type cmd, and press Enter.
Download the Git installer: Run the following command to download the latest version of Git for Windows:
```
powershell -Command "Invoke-WebRequest -Uri https://github.com/git-for-windows/git/releases/download/v2.37.0.windows.1/ Git-2.37.0.1-64-bit.exe -OutFile Git-2.37.0.1-64-bit.exe"
```

Replace the version number with the latest version available. 3. Install Git: Run the downloaded installer by typing:
```
Git-2.37.0.1-64-bit.exe
```

Follow the installation prompts to complete the installation. 4. Verify the installation: Open a new Command Prompt and type:
```
git --version
```

This should display the version of Git installed on your system.

###### **For macOS (using Homebrew):**

Open the Terminal: You can find Terminal in the Applications/Utilities folder, or use Spotlight to search for it.
Install Homebrew: If you don’t have Homebrew installed, run the following command:
```
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

Install Git: Run the following command to install Git using Homebrew:
```
brew install git
```

Verify the installation: Open a new Terminal and type:
```
git --version
```

This should display the version of Git installed on your system.

###### **For Linux:**

Open the Terminal: You can find Terminal in the Applications/Utilities folder, or use Spotlight to search for it.
Install Git: Run the following command to install Git:
```
sudo apt-get install git
```

For Ubuntu-based systems, use:
```
sudo apt-get update && sudo apt-get install git
```

For Red Hat-based systems, use:
```
sudo yum install git
```

Verify the installation: Open a new Terminal and type:
```
git --version
```

This should display the version of Git installed on your system

###### Download git using GUI:
Git is available for Windows, macOS, and Linux and is available at [Git Download](https://git-scm.com/downloads).

### Account Github
For this section click on [Github](#getting-started-with-github)


## Terminoly
### CHeck your git version
To check your git version, you can run the following command:

```
git --version
```

This  command will display the version of the git installed on your system.

Git is a very stable software and don't get any breaking changes in majority of the cases.

### Repository
A repository is a collection of files and directories that are stored together. It is away to store and manage your code.

A repository is like a folder on your computer, but it is more than just a folder.

It contain other files, folders, and evevn **other repositories**.

There is a difference betweeen a software on your system vs tracking a particular folderon your system.

At any point you can run the following command to see the current state of your repository
```
git status
```

There are two types of folders
1. Tracked folder
2. Untracked folder


### Your config setting
1. Setup your email and username in the config file
```
git config --global user.email "your-email@example.com"
git config --global user.name "Your Name"
```

2. Check your config setting
```
git config --list
```

This will show you all the setting that you have changed.

### Creating a repository
Creating a repository is a process of creating a new folder on your system and initializing it as a git repository. It’s just regular folder to code your project, you are just asking git to track it. 

To create a repository, you can use the following command:
```
git status
git init
```

`git status` command will show you the current state of your repository.

`git init` command will create a new folder on your system and initialise it as a git repository. This adds a hidden `.git` folder to your project.

### Commit
Commit is a way to save your chnages to your repository. It is a way to record your changes and make them permanent. 
Commit is just like a snaphot of your code at a particular point in time.
When you commit your changes, you are telling git to save them in a permanent way. This way, you can always go back to that point in time and see what you changed.

Usual flow is look like :
![alt text](commit-flow.png)

### Complte git flow
A complete git flow, along with pushing the code to github looks like this:
![alt text](complete-git-flow.png)

When you want to track a new folder, you first use `init` command to create a new repository. Then you can use `git add` command to add the folder to the repository. After that you can use  `commit` command to save the changes. Finally you can use the `push` command ti push the changes to github. Ofcourse there is more to it but this is the basic flow.

### Stage
Stage is a way to tell git to track a particular file or folder. You can use the following command to stage a file:
```
git init
git add <file1> <file2>
git status
```

Here we are initializing the repository and adding a file to the repository. Then we can see that the file is now being tracked by git. Currently our files are in staging area, this means that we have not yet committed the changes but are ready to be committed.


### Commit
```
git commit -m "commit message"
git status
```

Here we are committing the changes to the repository. We can see that the changes are now committed to the repository. The `-m` flag is used to add a message to the commit. This message is a short description of the changes that were made. You can use this message to remember what the changes were. Missing the `-m` flag will result in an action that opens your default settings editor, which is usually VIM. We can  change this to vscode or any other editor.

### Log
```
git log
```
This command will show you the history of your repository. It will show you all the commits that were made to the repository. You can use the `--oneline` flag to show only the commit message. This will make the output more compact and easier to read.

#### Atomic Commits
  Atomic commits are a way to make sure that each commit is a self-contained unit of work. This means that if one commit fails, you can always go back to a previous commit and fix the issue. This is important for maintaining a clean and organized history in your repository.

for more info : https://git-scm.com/docs/git-log

### Change default code editor
You can change the deafult code editor in your system to vscode. To do this, you can use the following command:
```
git config --global core.editor "code --wait"
```

### gitignore
Gitignore is a file that tells git which files and folders to ignore. It is a way to prevent git from tracking certain files or folders. You can create a gitignore file and add list of files and folders to ignore by using the following command:

Example:
```
node_module
.env
.vscode
```

Now, when you run the `git status` command, it will not show the `node_modules` and `.vscode` folders as being tracked by git.



## Git behind the scene (Git Internals)
Git is a version control system that allows you to track changes to your files and folders. It is a powerful tool that can help you manage your code more effectively. In this section, we will explore the basics of how git works internally.

### Git Snapshots
A git snapshot is a point in time in the history of your code. It represents a specific version of your code, including all the files and folders that were present at that time. Each snapshot is identified by a unique hash code, which is a string of characters that represents the contents of the snapshot.

A snapshot is not an image, it’s just a representation of the code at a specific point in time. Snapshot is a loose term that is used when git stores information about the code in a locally stored key-value based database. Everything is stored as an object and each object is identified by a unique hash code.

### 3 Musketeers of git
The three musketeers of git are;
- Commit Object
- Tree Object
- Blob Object

### Commit Object
Each commit in the project is stored in `.git` folder in the form of a commit object. A commit object contains the following information:
- Tree Object
- Parent Commit Object
- Author
- Committer
- Commit Message

### Tree Object
Tree Object is a container for all the files and  folders in the project. It contains the following
- File Mode
- File Name
- File Hash
- Parent Tree Object

Everything is stored as key-value pairs in the tree object. The key is the file name and the value is the file hash.

### Blob Object
Blob Object is present in the tree object and contains the actual file content. This is the place where the file content is stored.

![alt text](image.png)

### Helpfull Commands
Here are some helpfull commands that you can use to explore the **git internals**:
```
git log --oneline
```

Grab commit hash from  the above command and use it in the following command:
``` 
git show -s --pretty=raw <commit-hash>
```

Grab tree id from  the above command and use it in the following command to get the tree object:
```
git ls-tree <tree-id>
```

Grab blob id from  the above command and use it in the following command to get the blob object:
```
git show <blob-id>
```

Grab tree id from the above command and use it in the following command to get the commit object:
```
git cat-file -p <commit-id>
```

### Data in git 
Conceptually, the data that Git is storing looks something like this:
![alt-text](image-1.png)

![alt-text](image-2.png)

![alt text](image-3.png)

### Types of commands in git
1. Porcelain

![alt text](porcelain.png)

2. Plumbing

![alt text](plumbing.png)

3. Gardening Command (not sure about it)

### How to done things in git (without any interface)
```
git init
git status
touch example.txt
git status
```
Output is untracked files

To tracked the untracked file(stage version)
Before interface:
1. **Create unique commit id** (using a unique sha variable sha1)
```
sha1=$(git hash-object -w example.txt)
$sha1
```

2. **Maintaing the indexing of git**
```
git update-index --add --cacheinfo 100644 $sha1 example.txt
```

Now `example.txt` is added to staged area. You can check using:
```
git status
```
3. **Making tree**
```
tree=$(git write-tree)
commit=$(echo "Initial Commit" | git commit-tree $tree)
git update-ref HEAD $commit
```

Now `example.txt` is committed. You can check using :
```
git status
``` 
Nothing to commit is the output.

```
git log --online
```

## Branches in git
### Branches in git
branches are a way to work on different version of a project at the same time. They allow you to create  a separate line of development that can be worked on independently of the main branch. This can be useful when you want to make changes to a project without affecting the main branch or when you want to work on a new feature or bug fix.

![alt text](git-branch.png)

Some developers can work on Header, some can work on Footer, some can work on Content, and some can work on Layout. This is a good example of how branches can be used in git.

### HEAD in git
The `HEAD` is a pointer to the current branch that you are working on. It points to the latest commit in the current branch. When you create a new branch, it is automatically set as the `HEAD` of that branch.

**Note:** The default branch used to be called `master`, but it is now called `main`. There is nothing special about `main`; it is just a convention.

### Creating a new Branch
To create a new branch, you can use the following command
```
git branch
git branch bug-fix
git switch bug-fix
git log
git switch master
git switch -c dark-mode
git checkout orange-mode
```

Some points to note:
- `git branch` - This command lists all the branches in the current repository.
- `git branch bug-fix` - This command create a new branch called `bug-fix`.
- `git switch bug-fix` - This command switches to the `bug-fix` branch.
- `git log` - This command shows the commit history for the current branch.
- `git switch master` - This command switches to the master branch.
- `git switch -c dark-mode` - This command creates a new branch called `dark-mode`. the `-c` flag is used to create a new branch.
- `git checkout orange-mode` - This command switches to the orange-mode branch.
 - Commit before switching to a branch
 - Go to .git folder and checkout to the HEAD file


### Merging branches
#### **Fast_forward merge**
This one is easy as branch that you are trying to merge is usually ahead and there are no conflicts.

When you are done working on a branch, you can merge it back into the main branch. This is done using the following command:
```
git checkout main
git merge bug-fix
```
![alt text](fast-forward-merge.png)

Some points to note:
- `git checkout main` - This command switches to the `main` branch.
- `git merge bug-fix` - This command merges the `bug-fix` branch into the `main` branch.

This is a fast-forward merge. It means that the commit in the `bug-fix` branch are directly merged into the `main` branch. This can be useful when you want to merge a branch that has already been pushed to the remote repository.

#### **Not Fast-forward merge**


In this type of merge, the master branch also worked and have some commits that are not in the `bug-fix` branch. This is a not fast-forward merge.

When you are done working on a branch, you can merge it back into the main branch. This is done using the the following command:
``` 
git checkout main
git merge bug-fix
```
Since the command for the fast-forward and not fast-forward merge are same, the only difference between is how you resolve the conflicts.

In a fast-forward merge, there are no conflicts.But in a not fast-forward merge, there are conflicts, and there are no shortcuts to resolve them. You have to manually resolve the conflits. Decide, what to keep and what to discard. VSCode has a built-in merge tool that can help you resolve thr conflits.

![alt text](non-fast-forward.png)


### Managing conflits
There is no magic button to resolve conflicts. You have to manually resolve the conflits. Decide, what to keep and what to discard. VSCode has a built-in merge tool that can help you resolve the conflicts. I personally use VSCode merge tool. Github also has a merge tool that can help you resolve the conflicts but most of the time I handle them in VSCode and it gives me all the options to resolve the conflicts.

Overall it sounds scary to beginners but it is not, it’s all about communication and understanding the code situation with your team members.

### Rename a branch
You can rename a branch using the following command:
```
git branch -m <old-branch-name> <new-branch-name>
```

### Delete a branch
You can delete a branch using the following command:
```
git branch -d <branch-name>
```

### Checkout a branch
You can checkout a branch using the following command:
``` 
git checkout <branch-name>
```

Checkout a branch means that you are going to work on that branch, You can checkout any branch you want.

### List all branches
You can list all the branches using the following command:
```
git branch
```

List all the branch means that you are going to see all the branches in your repository.

## diff stash and Tags
### Git diff
The `git diff` is an **informative command** that shows the difference betweeen twoo commits. It is used to comapare the changes made in one commit with the changes made in another commit. Git consider the changed versions of the same file as two different files. Then it give names to these two files and shows the differneces between them.

### How to read the diff
- a -> file A and b -> file B
- ---- indicates the file A
- ++++ indicates the file B
- @@ indicates the line number

Here the file A and file B are the same file but different versions.

GIt will show you the cahnges made in the files A and file B. It will also show you the line number where the change occurred along with little preview of the change.

### Comparing Working Directory and Staging Area
```
git diff
```

This command shows the unstagd changes in your working directory compared to the staging area. This command alone will not show you the changes made in the file A and file B, you nedd to provide options to show the changes

### Comparing Staging Area with Repository
```
git diff --staged
```
This command shows the changes between your last commit and the staging area (i.e. changes that are staged and ready to be commiterd).

### Comparing between Branches
```
git diff <branch-name-one> <branch-name-two>
```
This command compares the difference between two branches.

Another way to compare the diifernce between two branches is to use the following command:
```
git diff branch-name-one..branch-name-two
```

### Comparing Specific Commits
```
git diff <commit-hash-one> <commit-hash-two>
```
This command compares the differnce between two commits.

### Git Stash
Stash is a way to save your changes ina  temporary location. It is useful when you want to make changes to a file but don't want to commit them yet. You can then came back to the file later and apply the changes.

**Note** Conflicting changes will not allow you to switch branches without commiting the changes in a temporary location.

```
git stash
```
This command saves your changes in a temporary loaction. It is like a stack of changes that you can access later.

### Naming the stash
You can also name the stash by using the following command:
```
git stash save "work in progress on X feature"
```

### View the stash list
YOu can view the list of stashes by using the following command:
```
git stash list
```

### Apply the stash
You can apply the stash by using the following command:
```
git stash apply 
```

### Apply the specific stash
You can apply the specific stash by using the following command:
```
git stash apply stash@{0}
```
Here `stash@{0}` is the name of the stash. You can use the `git stash list` command to get the name of the stash.

### Applying and dropping the stash
You can apply and drop the stash by using the following command:
```
git stash pop
```
This command applies the stash and drops it from the stash list

### Drop the Stash
You can drop the stash by using the following command:
```
git stash drop
```

### Applying stash to a specific branch
You can apply the stash to a specific branch by using the following command:
```
git stash apply stash@{0} <branch-name>
```

### Clearing the stash
You can clear the stash by using the following command:
```
git stash clear
```

### Git Tags
Tags are a way to mark a specific point in your repository. They are useful when you want to remember a specific version of your code or when you want to refers  to a specific commit. Tags are like sticky notes that you can attach to your commits.

### Creating a tag
You can create a tag using the following command:
```
git tag <tag-name>
```
This command creates a new tag with the specific name. The tag will be attached to the current commit.

### Create an annotated tag
You can create an annotated tag using the following command:
```
git tag -a <tag-name> -m "Release 1.0"
```
This  Command creates an annoted tag with the specific name and message. The tag will be attached to the current commit.

### List all tags
You can list all tag using the following command:
```
git tag
```
This command lists all the tags in your repository.

### Tagging a specific commit
You can tag a specific commit using the following command:
```
git tag <tag-name> <commit-hash>
```

### Push tags to remote repository
You can push tags to a remote repository using the following command:
```
git push origin <tag-name>
```

### Delete a tag
You can delete a tag on a remote repository using the following command:
```
git push origin :<tag-name>
```

## Rebase and reflog
### Rebase in git
Git rebase is a powerful Git feature used to change the base of a branch. It effectively allow you to move a branch to a new starting point, usually a different commit, by "replying" the commits from the original base onto the new base. This can be useful for keeping a cleaner, linear project history.

Some people like to use rebase over the merge command because it allows you to keep the commit history cleaner and easier to understand. It allows you to make changes to the code without affecting the original branch.

### Merge commits
A merge commit is a commit that combines two or more commits into one. It is created when you merge two or more branches into a single branch. The merge contains all the changes from the original branches, and it is used to keep the project history clean and easy to understand.

![alt text](merge-commits.png)

### Rebase
![alt text](rebase.png)
Rebase is a poweful tool in Git that allows you to move a branch to a new starting point. It effectively replays the commits from the original base onto the new base. This can be useful foe keeping a cleaner, linear project history.

Here's a flow example of using git rebase with all the commands involved:

Suppose you hae a feature branch called **feature-branch** that you want to rebase onto the main branch.

### Ensure you  are on the branch that you want to rebase:
```
git checkout feature-branch
git rebase main
```
Here `feature-branch` is the branch that you  want to rebase. `main` is the branch from that you want to rebase the `feature-branch`.

This will replay the commits from `feature-branch` on top of the latest change in main.

### Resolve any conflicts:
If there are any conflicts, you will need to resolve them manually. You can use the merge tool in VSCode to resolve  the conflicts.
```
git add <resolve-files>
git rebase --continue
```
> **Note:** Try to avoid using the `--force` option when using `git rebase`. It can cause issues with the project history. Many horror stories involve people using `--force` to fix conflicts.
 

### Git reflog
Git reflog is a command that shows you the history of your commits. It allows you to see the changes that you have made to your repository over time. This can be useful for debugging and understanding the history of your project.

### View the reflog
```
git reflog
```
This willshow you the history of your commits. You can use the number at the end of each line to access the commit that you want to view.

### Find specific commit
You can find a specific commit using the following command:
```
git reflog <commit-hash>
```
Or you can use `HEAD@{n}` to reset to the nth commit before the one you want to reset to.
```
git rebase <commit-hash>
git reset --hard HEAD@{n}
```

## Getting started with Github
### What is Github?
Github is web-based GIt repository hosting service. Ti is a popular platform for developers to collaborate on projects and to share code. Github provides a user-friendly interface for managing and tracking changes to your code, as well as a platform for hosting and sharing your projects with others.

Some other alternative of Github are:
- Gitlab
- Bitbucket
- Azure Repos
- Gitea
But mainstream popular tool these days is Github.

### Github Account
Creating a Github account is free and easy. YOu can create an account by visiting the [Github website]https://github.com/) and clicking on the **"Sign Up"** button. You will be promoted to enter your email address and password, and then you will be redirected to the Github homepage.

Once you have created an account, you can start using Github to host and collaborate on your projects. Github provides a variety of features and tools that make it easy to manage and track your code, including issues, pull requests, and code reviews.

### Configure your config file
If you haven't done it already, youneed to configure your git config file. You can do this by running the following command:
```
git config --global user.email "your-email@example.com"
git config --global user.name "Your name"
```
This will set your email and name as your as your global setting. You can change these settings later by running the following command:
```
git config --global user.email "your-email@exmaple.com"
git config --global user.name "Your name"
```
Now you can check your config setting :
```
git config --lilst
```
This will show you all the settings that you have changed.

### Setup ssh key and add to github
If you haven't done it already, you need to setup ssh key and add it to your github account. You can do this by following the intructions on the [github website](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent) 

You can find the exact steps on the website for both Windows, Linux and MacOS. The steps are same for both, only macOS users need to add the ssh key to their keychain.

#### Step 1: Generate a new SSH key
To generate a new SSH key, open the terminal and run the following command :
```
ssh-keygen -t ed25519 -C "your-email@example.com"
```
Here `ed25519` is the type of key that you are generating. This creates a new SSH key, suing the provided email as label.

#### Step 2: Save the key
After generating the key, you need to save it to your computer. You can do this by running the following :
> **Note** Enter a file in which to save the key (/Users/YOU/.ssh/id_ALGORITHM): [Press enter]

At the prompt you can enter passphrase for the key or you can leave it blank.  If you leave it blank, the key will be saved without a passphrase.

#### Step 3: Add key to your ssh-agent
After saving the key, you need to add it to your ssh-agent. You can do this by running the following command:

For this refer to Github, github has a lot of information on this.

#### 4. Add key to Github
Use the webui to add key to your github account. You can do this by following the instructions on the [Github website](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/adding-a-new-ssh-key-to-your-github-account?tool=webui) 

### Adding code to remote repository
Now after setup of your ssh key and added it to your github account, you can start pushing your code to the remote repository.

Create a new Repo on your system first, add some code and commit it.
```
git init
git add <file-name>
git commit -m "commit message"
```

#### Check remote URL Setting
```
git remote -v
```
This will show you the remote url of your repository.

#### Add remote repository
You can add a remote repository by running the following command:
```
git remote add origin <remote-url>
```
Here `remote-url` is the url of the remote repository that you want to add and `origin` is the name of the remote repository. Thia origin is used to refer to the remote repository in the future.

#### Push code to remote repository
```
git push remote-name branch-name
```
Here `remote-name` is the nmae of the remote that you want to push to and `branch-name` is the name of the branch that you want to push.
```
git push origin main
```

#### Setup an upstream remote
Setting up an upstream remote is useful when you want to keep your local repository up to date with the remote repository. It allows you to fetch and merge change from the remote repository into your local repository.

To set up an remote,you can use the following command:
```
git remote add upstream <remote-url>
```
Or you can use the **shortcut**
```
git remote add -u <remote-url>
```
You can do this at the time of pushing your code to the remote repository.
```
git push -u origin main
```

This will setup an upstream remote and push your code to the remote repository.

This will allow you run future command like `git pull` and `git push` wihout specifying the remote name.

### Get code from remote repository
There are two ways to get code from a remote from repository :
- fetch the code
- pull the code

`Fetch` the code means that you are going to download the code from the remote repository to your local repository. 

`Pull` the code means that you are going to download the code from the remote repository and merge it with your local repository.

![alt text](code-from-remote.png)


### Fetch code
To fetcg code from a remote repository, youcan use the following command :
```
git fetch <remote-name>
```
Here `remote-name` is the name of the remote repository that you want to fetch from.

### PUll code
To pull code froma remote repository, you can use the following command :
```
# git pull <remote-name> <branch-name>
git pull origin main
```
Here `remote-nmae` is the name of the remote repository that you want to pull. 

