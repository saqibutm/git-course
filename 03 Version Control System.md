**VCS** - By keeping track of the changes that we make to our files, a VCS lets us know when a file changed, who changed it, and also lets us easily roll back those changes.

**git** - Developed in 2005 by Linus Torvalds who stared Linux which is a distributed system and does not rely on a central server. Git-scm sum stands for **Source Control Management**. For more information about git 
-   [https://git-scm.com/doc](https://git-scm.com/doc)
-   [https://www.mercurial-scm.org/](https://www.mercurial-scm.org/)
-   [https://subversion.apache.org/](https://subversion.apache.org/)
-   [https://en.wikipedia.org/wiki/Version\_control](https://en.wikipedia.org/wiki/Version_control)

**Git - Installation**
The first step on the way to using Git is to install it! The directions found in the Git documentation below are pretty thorough and helpful, check them out for the best method of getting Git onto your platform of choice.

-   [Git download page](https://git-scm.com/downloads)
-   [Git installation instructions for each platform](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git)

**Git Configuration**
```Shell
git config --global user.email “myemail@gmail.com”
git config --global user.name “my name”
git config -l
````

**How to Start with git?**
```Shell
mkdir myfolder
cd myfolder
git init
ls -la
ls -l .git/
```
The git directory contains all the changes and their history and the working tree contains the current versions of the files.
![[git_directory.png]]
First we add the files to staging area using git add file_name or git add . command. The staging area which is also known as the index is a file maintained by Git that contains all of the information about what files and changes are going to go into your next commit command. We can use the git status command to get some information about the current working tree and pending changes. 
```Shell
git add file_name
git status
git commit -m "Added new file"
git status
```
Any Git project will consist of three sections. The Git directory, the working tree, and the staging area. The Git directory contains the history of all the files and changes. The working tree contains the current state of the project, including any changes that we've made. And the staging area contains the changes that have been marked to be included in the next commit. 
![[git_workflow.png]]
Now, let's dive into the details of how we track changes to our files. When we operate with Git, our files can be either tracked or untracked. Tracked files are part of the snapshots, while untracked files aren't a part of snapshots yet. This is the usual case for new files. Each track file can be in one of three main states, modified, staged or committed. Let's look at what each of these mean. 

**Anatomy of a Commit Message**
A commit message is generally broken up into a few sections. The first line is a short summary of the commit followed by a blank line. This is followed by a full description of the changes which details why they're necessary and anything that might be especially interesting about them or difficult to understand. *git log* shows us the list of commits made in the current Git  repository. By default, it prints the commit message, the author, and the date of the change.
![[git_log.png]]
Initial Git Cheat Sheet
Check out the following links for more information:
The Linux kernel documentation itself, as well as impassioned opinions from other developers.  
You can check out "Setting your email in Git" and "Keeping your email address private" on the GitHub help site for how to do this.

**Initial Git Cheat Sheet**
The [Linux kernel documentation](https://git.kernel.org/pub/scm/linux/kernel/git/torvalds/linux.git/tree/Documentation/process/submitting-patches.rst?id=HEAD) itself, as well as [impassioned](http://stopwritingramblingcommitmessages.com/) opinions from other [developers](https://robots.thoughtbot.com/5-useful-tips-for-a-better-commit-message). 
You can check out "[Setting your email in Git](https://help.github.com/articles/setting-your-email-in-git/)" and "[Keeping your email address private](https://help.github.com/articles/keeping-your-email-address-private/)" on the GitHub help site for how to do this.

**Skipping the Staging Area**
-a with commit skips the staging area and directly commit all the changes. However, it only works with previously tracked files. For new files, we need to track them first by using add command. Further, it only good for small changes. Long descriptions can not be added while using -a in commit message. 
-m flag shows added lines with pluses and remove lines with dashes. 
Because the amount of text is now longer than what fits on your screen, 
Git automatically uses a paging tool that allows us to scroll using page up, 
page down, and the arrow keys. 
```Script
# To skip the stagging area.
git commit -a -m "Added a file"

# Give the list of the commits
git log 

# give the details of the patch
git log -p 

git show commit_id
git log --stat
```

**To. view the changes before adding them**
