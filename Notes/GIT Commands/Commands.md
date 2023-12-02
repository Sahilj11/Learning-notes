- You can view all of your settings and where they are coming from using:
  `git config --list --show-origin`

- The first thing you should do when you install Git is to set your user name and email address. This is important because every Git commit uses this information, and it’s immutably baked into the commits you start creating:

```
$ git config --global user.name "John Doe"
$ git config --global user.email johndoe@example.com
```

- Again, you need to do this only once if you pass the --global option, because then Git will always
  use that information for anything you do on that system. If you want to override this with a
  different name or email address for specific projects, you can run the command without the
  --global option when you’re in that project.

- Now that your identity is set up, you can configure the default text editor that will be used when Git needs you to type in a message. If not configured, Git uses your system’s default editor.

```
git config --global core.editor emacs
```

- On a Windows system, if you want to use a different text editor, you must specify the full path to its executable file

```
git config --global core.editor "'C:/Program Files/Notepad++/notepad++.exe'
```

- By default Git will create a branch called master when you create a new repository with git init. From Git version 2.28 onwards, you can set a different name for the initial branch. To set main as the default branch name do:
- `git config --global init.defaultBranch main`

- If you want to check your configuration settings, you can use the `git config --list `command to list all the settings Git can find at that point:

You can also check what Git thinks a specific key’s value is by typing git config `<key>`:

```
$ git config user.name
John Doe
```

You may see keys more than once, because Git reads the same key from different files
([path]/etc/gitconfig and ~/.gitconfig, for example). In this case, Git uses the last value for each unique key it sees.

Since Git might read the same configuration variable value from more than one
file, it’s possible that you have an unexpected value for one of these values and
you don’t know why. In cases like that, you can query Git as to the origin for that
value, and it will tell you which configuration file had the final say in setting that
value:

```
$ git config --show-origin rerere.autoUpdate
file:/home/johndoe/.gitconfig false
```

If you ever need help while using Git, there are three equivalent ways to get the comprehensive manual page (manpage) help for any of the Git commands:

```
$ git help <verb> // git help config
$ git <verb> --help
$ man git-<verb>
```

These commands are nice because you can access them anywhere, even offline. If the manpages and this book aren’t enough and you need in-person help, you can try the #git, #github, or #gitlab channels on the Libera Chat IRC server, which can be found at https://libera.chat/. These channels are regularly filled with hundreds of people who are all very knowledgeable about Git and are often willing to help.

In addition, if you don’t need the full-blown manpage help, but just need a quick refresher on the available options for a Git command, you can ask for the more concise “help” output with the -h option,
`git add -h`

### Initialising a repo in existing directory

- If you have a project directory that is currently not under version control and you want to start controlling it with Git, you first need to go to that project’s directory. If you’ve never done this, it looks a little different depending on which system you’re running:
- `git init`
- If you want to start version-controlling existing files (as opposed to an empty directory), you should probably begin tracking those files and do an initial commit. You can accomplish that with a few git add commands that specify the files you want to track, followed by a git commit:

```
$ git add *.c
$ git add LICENSE
$ git commit -m 'Initial project version'
```

### Cloning an Existing Repository

- If you want to get a copy of an existing Git repository — for example, a project you’d like to contribute to — the command you need is git clone. If you’re familiar with other VCSs such as Subversion, you’ll notice that the command is "clone" and not "checkout". This is an important distinction — instead of getting just a working copy, Git receives a full copy of nearly all data that the server has. Every version of every file for the history of the project is pulled down by default when you run git clone. In fact, if your server disk gets corrupted, you can often use nearly any of the clones on any client to set the server back to the state it was in when it was cloned (you may lose some server-side hooks and such, but all the versioned data would be there
- You clone a repository with git clone `<url>.` For example, if you want to clone the Git linkable library called libgit2, you can do so like this:
- ` $ git clone https://github.com/libgit2/libgit2`
- That creates a directory named libgit2, initializes a .git directory inside it, pulls down all the data for that repository, and checks out a working copy of the latest version. If you go into the new libgit2 directory that was just created, you’ll see the project files in there, ready to be worked on or used.
- If you want to clone the repository into a directory named something other than libgit2, you can specify the new directory name as an additional argument:
- `$ git clone https://github.com/libgit2/libgit2 mylibgit`

### Recording Changes to the Repository

- Remember that each file in your working directory can be in one of two states: tracked or
  untracked. Tracked files are files that were in the last snapshot, as well as any newly staged files; they can be unmodified, modified, or staged. In short, tracked files are files that Git knows about
- Untracked files are everything else — any files in your working directory that were not in your last snapshot and are not in your staging area. When you first clone a repository, all of your files will be tracked and unmodified because Git just checked them out and you haven’t edited anything

### Checking the Status of Your Files

- The main tool you use to determine which files are in which state is the git status command. If you
  run this command directly after a clone, you should see something like this:

```
$ git status
On branch master
Your branch is up-to-date with 'origin/master'.
nothing to commit, working tree clean
```

This means you have a clean working directory; in other words, none of your tracked files are modified. Git also doesn’t see any untracked files, or they would be listed here. Finally, the command tells you which branch you’re on and informs you that it has not diverged from the same
Untracked basically means that Git sees a file you didn’t have in the previous
snapshot (commit), and which hasn’t yet been staged; Git won’t start including it in your commit
snapshots until you explicitly tell it to do so.

### Tracking New Files

- In order to begin tracking a new file, you use the command git add. To begin tracking the README file, you can run this:
- `$ git add README`

### Staging modified files

```
$ git status
On branch master
Your branch is up-to-date with 'origin/master'.
Changes to be committed:
(use "git reset HEAD <file>..." to unstage)
new file: README
Changes not staged for commit:
(use "git add <file>..." to update what will be committed)
(use "git checkout -- <file>..." to discard changes in working directory)
modified: CONTRIBUTING.md
```

The CONTRIBUTING.md file appears under a section named “Changes not staged for commit” — which
means that a file that is tracked has been modified in the working directory but not yet staged. To
stage it, you run the git add command. git add is a multipurpose command — you use it to begin
tracking new files, to stage files, and to do other things like marking merge-conflicted files as
resolved. It may be helpful to think of it more as “add precisely this content to the next commit”
rather than “add this file to the project”

You open it again and
make that change, and you’re ready to commit. However, let’s run git status one more time

```
$ vim CONTRIBUTING.md
$ git status
On branch master
Your branch is up-to-date with 'origin/master'.
Changes to be committed:
(use "git reset HEAD <file>..." to unstage)
new file: README
modified: CONTRIBUTING.md
Changes not staged for commit:
(use "git add <file>..." to update what will be committed)
(use "git checkout -- <file>..." to discard changes in working directory)
modified: CONTRIBUTING.md

```

Now CONTRIBUTING.md is listed as both staged and unstaged. How is that possible? It
turns out that Git stages a file exactly as it is when you run the git add command. If you commit
now, the version of CONTRIBUTING.md as it was when you last ran the git add command is how it will
go into the commit, not the version of the file as it looks in your working directory when you run
git commit. If you modify a file after you run git add, you have to run git add again to stage the
latest version of the file

### Short status

- Git also has a short
  status flag so you can see your changes in a more compact way. If you run git status -s or git
  status --short you get a far more simplified output from the command:

```
$ git status -s
M README
MM Rakefile
A lib/git.rb
M lib/simplegit.rb
?? LICENSE.txt
```

New files that aren’t tracked have a ?? next to them, new files that have been added to the staging
area have an A, modified files have an M and so on. There are two columns to the output — the lefthand
column indicates the status of the staging area and the right-hand column indicates the status
of the working tree. So for example in that output, the README file is modified in the working
directory but not yet staged, while the lib/simplegit.rb file is modified and staged. The Rakefile
was modified, staged and then modified again, so there are changes to it that are both staged and
unstaged.

### Ignore files

```
$ cat .gitignore
*.[oa]
*~
```

The first line tells Git to ignore any files ending in “.o” or “.a” — object and archive files that may be
the product of building your code. The second line tells Git to ignore all files whose names end with
a tilde (~), which is used by many text editors such as Emacs to mark temporary files. You may also
include a log, tmp, or pid directory; automatically generated documentation; and so on. Setting up a
.gitignore file for your new repository before you get going is generally a good idea so you don’t
accidentally commit files that you really don’t want in your Git repository

The rules for the patterns you can put in the .gitignore file are as follows:
• Blank lines or lines starting with # are ignored.
• Standard glob patterns work, and will be applied recursively throughout the entire working
tree.
• You can start patterns with a forward slash (/) to avoid recursivity.
• You can end patterns with a forward slash (/) to specify a directory.
• You can negate a pattern by starting it with an exclamation point (!).
Glob patterns are like simplified regular expressions that shells use. An asterisk (\*) matches zero or
more characters; [abc] matches any character inside the brackets (in this case a, b, or c); a question
mark (?) matches a single character; and brackets enclosing characters separated by a hyphen ([0-
9]) matches any character between them (in this case 0 through 9). You can also use two asterisks to
match nested directories; a/\*\*/z would match a/z, a/b/z, a/b/c/z, and so on.

```
# ignore all .a files
*.a
# but do track lib.a, even though you're ignoring .a files above
!lib.a
# only ignore the TODO file in the current directory, not subdir/TODO
/TODO
# ignore all files in any directory named build
build/
# ignore doc/notes.txt, but not doc/server/arch.txt
doc/*.txt
# ignore all .pdf files in the doc/ directory and any of its subdirectories
doc/**/*.pdf
```

### Viewing your staged and unstaged changes

If the git status command is too vague for you — you want to know exactly what you changed, not
just which files were changed — you can use the git diff command. We’ll cover git diff in more
detail later, but you’ll probably use it most often to answer these two questions: What have you
changed but not yet staged? And what have you staged that you are about to commit? Although git
status answers those questions very generally by listing the file names, git diff shows you the
exact lines added and removed — the patch, as it were.
To see what you’ve changed but not yet staged, type git diff with no other arguments
That command compares what is in your working directory with what is in your staging area. The
result tells you the changes you’ve made that you haven’t yet staged.
If you want to see what you’ve staged that will go into your next commit, you can use `git diff--staged`. (you can also use --cached instead of --staged)This command compares your staged changes to your last commit:

It’s important to note that git diff by itself doesn’t show all changes made since your last
commit — only changes that are still unstaged. If you’ve staged all of your changes, git diff will
give you no output.

## Skipping the staging area

Although it can be amazingly useful for crafting commits exactly how you want them, the staging
area is sometimes a bit more complex than you need in your workflow. If you want to skip the
staging area, Git provides a simple shortcut. Adding the -a option to the git commit command makes
Git automatically stage every file that is already tracked before doing the commit, letting you skip
the git add part:

```
$ git status
On branch master
Your branch is up-to-date with 'origin/master'.
Changes not staged for commit:
(use "git add <file>..." to update what will be committed)
(use "git checkout -- <file>..." to discard changes in working directory)
modified: CONTRIBUTING.md
no changes added to commit (use "git add" and/or "git commit -a")
$ git commit -a -m 'Add new benchmarks'
[master 83e38c7] Add new benchmarks
```

Notice how you don’t have to run git add on the CONTRIBUTING.md file in this case before you commit.
That’s because the -a flag includes all changed files. This is convenient, but be careful; sometimes
this flag will cause you to include unwanted changes.

## removing files

To remove a file from Git, you have to remove it from your tracked files (more accurately, remove it
from your staging area) and then commit. The git rm command does that, and also removes the file
from your working directory so you don’t see it as an untracked file the next time around.
If you simply remove the file from your working directory, it shows up under the “Changes not
staged for commit” (that is, unstaged) area of your git status output:

```
$ rm PROJECTS.md
$ git status
On branch master
Your branch is up-to-date with 'origin/master'.
Changes not staged for commit:
(use "git add/rm <file>..." to update what will be committed)
(use "git checkout -- <file>..." to discard changes in working directory)
deleted: PROJECTS.md
no changes added to commit (use "git add" and/or "git commit -a")
```

Then, if you run git rm, it stages the file’s removal:

```
$ git rm PROJECTS.md
rm 'PROJECTS.md'
$ git status
On branch master
Your branch is up-to-date with 'origin/master'.
Changes to be committed:
(use "git reset HEAD <file>..." to unstage)
deleted: PROJECTS.md
```

The next time you commit, the file will be gone and no longer tracked. If you modified the file or
had already added it to the staging area, you must force the removal with the -f option. This is a
safety feature to prevent accidental removal of data that hasn’t yet been recorded in a snapshot and
that can’t be recovered from Git.

Another useful thing you may want to do is to keep the file in your working tree but remove it from
your staging area. In other words, you may want to keep the file on your hard drive but not have
Git track it anymore. This is particularly useful if you forgot to add something to your .gitignore
file and accidentally staged it, like a large log file or a bunch of .a compiled files. To do this, use the
--cached option:

```
$ git rm --cached README
```

## Moving files

If you want to rename a file in Git, you can run
something like:

```
$ git mv file_from file_to
```

## Viewing commit history

The most basic and powerful
tool to do this is the git log command.
When you run git log in this project, you should get output that looks something like this:

```
$ git log
commit ca82a6dff817ec66f44342007202690a93763949
Author: Scott Chacon <schacon@gee-mail.com>
Date: Mon Mar 17 21:52:11 2008 -0700
Change version number
commit 085bb3bcb608e1e8451d4b2432f8ecbe6306e7e7
Author: Scott Chacon <schacon@gee-mail.com>
Date: Sat Mar 15 16:40:33 2008 -0700
Remove unnecessary test
commit a11bef06a3f659402fe7563abf99ad00de2209e6
Author: Scott Chacon <schacon@gee-mail.com>
Date: Sat Mar 15 10:31:28 2008 -0700
Initial commit
```

By default, with no arguments, git log lists the commits made in that repository in reverse
chronological order; that is, the most recent commits show up first. As you can see, this command
lists each commit with its SHA-1 checksum, the author’s name and email, the date written, and the
commit message.
One of the more helpful options is -p or --patch, which shows the difference (the patch output)
introduced in each commit. You can also limit the number of log entries displayed, such as using -2
to show only the last two entries

```
$ git log -p -2
commit ca82a6dff817ec66f44342007202690a93763949
Author: Scott Chacon <schacon@gee-mail.com>
Date: Mon Mar 17 21:52:11 2008 -0700
Change version number
diff --git a/Rakefile b/Rakefile
index a874b73..8f94139 100644
--- a/Rakefile
+++ b/Rakefile
@@ -5,7 +5,7 @@ require 'rake/gempackagetask'
spec = Gem::Specification.new do |s|
s.platform = Gem::Platform::RUBY
s.name = "simplegit"
- s.version = "0.1.0"
+ s.version = "0.1.1"
s.author = "Scott Chacon"
s.email = "schacon@gee-mail.com"
s.summary = "A simple gem for using Git in Ruby code."
commit 085bb3bcb608e1e8451d4b2432f8ecbe6306e7e7
Author: Scott Chacon <schacon@gee-mail.com>
Date: Sat Mar 15 16:40:33 2008 -0700
Remove unnecessary test
diff --git a/lib/simplegit.rb b/lib/simplegit.rb
index a0a60ae..47c6340 100644
--- a/lib/simplegit.rb
+++ b/lib/simplegit.rb
@@ -18,8 +18,3 @@ class SimpleGit
end
end
-
-if $0 == __FILE__
- git = SimpleGit.new
- puts git.show
-end
```

This option displays the same information but with a diff directly following each entry. This is very
helpful for code review or to quickly browse what happened during a series of commits that a
collaborator has added. You can also use a series of summarizing options with git log. For
example, if you want to see some abbreviated stats for each commit, you can use the --stat option:

Another really useful option is --pretty. This option changes the log output to formats other than
the default. A few prebuilt option values are available for you to use. The oneline value for this
option prints each commit on a single line, which is useful if you’re looking at a lot of commits. In
addition, the short, full, and fuller values show the output in roughly the same format but with
less or more information, respectively:

```
$ git log --pretty=oneline
ca82a6dff817ec66f44342007202690a93763949 Change version number
085bb3bcb608e1e8451d4b2432f8ecbe6306e7e7 Remove unnecessary test
a11bef06a3f659402fe7563abf99ad00de2209e6 Initial commit
```

The most interesting option value is format, which allows you to specify your own log output
format. This is especially useful when you’re generating output for machine parsing — because you
specify the format explicitly, you know it won’t change with updates to Git:

```
$ git log --pretty=format:"%h - %an, %ar : %s"
ca82a6d - Scott Chacon, 6 years ago : Change version number
085bb3b - Scott Chacon, 6 years ago : Remove unnecessary test
a11bef0 - Scott Chacon, 6 years ago : Initial commit
```

![](../../../statics/Pasted%20image%2020230819130232.png)
The oneline and format option values are particularly useful with another log option called --graph.
This option adds a nice little ASCII graph showing your branch and merge history:
`git log --pretty=format:"%h %s" --graph`

![](../../../statics/Pasted%20image%2020230819130419.png)

## Limiting Log Output

However, the time-limiting options such as --since and --until are very useful. For example, this
command gets the list of commits made in the last two weeks:

`$ git log --since=2.weeks`
This command works with lots of formats — you can specify a specific date like "2008-01-15", or a
relative date such as "2 years 1 day 3 minutes ago".
You can also filter the list to commits that match some search criteria. The --author option allows
you to filter on a specific author, and the --grep option lets you search for keywords in the commit
messages.

Another really helpful filter is the -S option (colloquially referred to as Git’s “pickaxe” option),
which takes a string and shows only those commits that changed the number of occurrences of that
string. For instance, if you wanted to find the last commit that added or removed a reference to a
specific function, you could call:
`$ git log -S function_name`

The last really useful option to pass to git log as a filter is a path. If you specify a directory or file
name, you can limit the log output to commits that introduced a change to those files. This is always
the last option and is generally preceded by double dashes (--) to separate the paths from the
options:
`$ git log -- path/to/file`

![](../../../statics/Pasted%20image%2020230819130928.png)

## undoing things

Be careful, because you can’t always undo some of these undos. This is
one of the few areas in Git where you may lose some work if you do it wrong.
One of the common undos takes place when you commit too early and possibly forget to add some
files, or you mess up your commit message. If you want to redo that commit, make the additional
changes you forgot, stage them, and commit again using the --amend option

$ git commit --amend

This command takes your staging area and uses it for the commit. If you’ve made no changes since your last commit (for instance, you run this command immediately after your previous commit), then your snapshot will look exactly the same, and all you’ll change is your commit message.
The same commit-message editor fires up, but it already contains the message of your previous commit. You can edit the message the same as always, but it overwrites your previous commit.
As an example, if you commit and then realize you forgot to stage the changes in a file you wanted to add to this commit, you can do something like this:

```
$ git commit -m 'Initial commit'
$ git add forgotten_file
$ git commit --amend
```

You end up with a single commit — the second commit replaces the results of the first.

### Unstaging a staged file

Right below the “Changes to be committed” text, it says use git reset HEAD `<file>`… to unstage. So,
let’s use that advice to unstage the CONTRIBUTING.md file:

### Unmodifying a modified file

What if you realize that you don’t want to keep your changes to the CONTRIBUTING.md file? How can
you easily unmodify it — revert it back to what it looked like when you last committed (or initially
cloned, or however you got it into your working directory)?

`git checkout -- CONTRIBUTING.md`

## Working with remotes

Remote repositories are versions of your project that are hosted on the Internet or
network somewhere. You can have several of them, each of which generally is either read-only or
read/write for you. Collaborating with others involves managing these remote repositories and
pushing and pulling data to and from them when you need to share work.

### Showing your remotes

To see which remote servers you have configured, you can run the git remote command. It lists the
shortnames of each remote handle you’ve specified. If you’ve cloned your repository, you should at
least see origin — that is the default name Git gives to the server you cloned from:

```
$ git clone https://github.com/schacon/ticgit
Cloning into 'ticgit'...
remote: Reusing existing pack: 1857, done.
remote: Total 1857 (delta 0), reused 0 (delta 0)
Receiving objects: 100% (1857/1857), 374.35 KiB | 268.00 KiB/s, done.
Resolving deltas: 100% (772/772), done.
Checking connectivity... done.
$ cd ticgit
$ git remote
origin
```

You can also specify -v, which shows you the URLs that Git has stored for the shortname to be used when reading and writing to that remote:

```
$ git remote -v
origin https://github.com/schacon/ticgit (fetch)
origin https://github.com/schacon/ticgit (push)
```

### adding remote repositories

We’ve mentioned and given some demonstrations of how the git clone command implicitly adds
the origin remote for you. Here’s how to add a new remote explicitly. To add a new remote Git
repository as a shortname you can reference easily, run git remote add `<shortname> <url>:
`

```
$ git remote
origin
$ git remote add pb https://github.com/paulboone/ticgit
$ git remote -v
origin https://github.com/schacon/ticgit (fetch)
origin https://github.com/schacon/ticgit (push)
pb https://github.com/paulboone/ticgit (fetch)
pb https://github.com/paulboone/ticgit (push)
```

Now you can use the string pb on the command line in lieu of the whole URL. For example, if you
want to fetch all the information that Paul has but that you don’t yet have in your repository, you
can run git fetch pb

```
$ git fetch pb
remote: Counting objects: 43, done.
remote: Compressing objects: 100% (36/36), done.
remote: Total 43 (delta 10), reused 31 (delta 5)
Unpacking objects: 100% (43/43), done.
From https://github.com/paulboone/ticgit
* [new branch] master -> pb/master
* [new branch] ticgit -> pb/ticgit
```

#### Git pull explained

Certainly! This explanation breaks down the quoted text about using the `git pull` command in Git:

1. **Tracking Remote Branches:** When you're working with Git, your codebase is typically stored in a remote repository (like on GitHub) and a local copy on your machine. A "branch" is a separate line of development that allows you to work on different features or changes independently.

2. **Setting Up Tracking:** When you set up a local branch to "track" a remote branch, it means that Git knows which remote branch corresponds to your local branch. This allows you to easily synchronize your work with the remote repository.

3. **Automatic Fetch and Merge:** The `git pull` command serves as a convenient way to update your local branch with the latest changes from the remote branch it's tracking. Here's how it works:

   - **Fetch:** It first fetches the latest changes from the remote repository. This means it retrieves any new commits made to the remote branch since you last updated your local branch.
   - **Merge:** After fetching, Git attempts to automatically merge the changes it fetched into your current local branch. If there are any conflicting changes (changes that can't be automatically merged), Git will notify you, and you'll need to manually resolve those conflicts.

4. **Advantages of `git pull`:** This process simplifies keeping your local branch up to date with the latest remote changes. It's especially useful when multiple people are collaborating on the same codebase because everyone can work on their own branches and use `git pull` to integrate the latest changes.

5. **Default Branch Tracking:** When you clone a remote repository using the `git clone` command, Git automatically sets up your local default branch (usually `master` or `main`) to track the remote repository's default branch. This means that you can immediately use `git pull` to fetch and merge updates from the remote repository.

6. **Workflow Convenience:** Using `git pull` can make your workflow smoother. Instead of manually downloading changes from the remote repository and figuring out how to integrate them, Git does this process for you automatically.

7. **Cautions:** While `git pull` is convenient, it's important to review the changes it fetches and merges. Sometimes, manual conflict resolution might be needed if the changes on the remote branch conflict with your local changes.

In summary, the `git pull` command simplifies the process of updating your local branch with changes from a remote branch. It's a helpful command when collaborating on projects and trying to keep your codebase up to date.

#### Git pull further explained

Certainly! The quoted text explains changes in the behavior of the `git pull` command starting from Git version 2.27, regarding the `pull.rebase` configuration variable and its impact on the behavior of `git pull`.

1. **Git Pull Behavior Explanation:**

   - `git pull` is a command used to fetch remote changes and integrate them into your current branch.
   - By default, Git tries to perform a "fast-forward" merge if possible. This means if your local branch has not diverged from the remote branch, Git simply moves your local branch pointer forward to match the remote branch's pointer. This results in a linear history.
   - If a fast-forward merge is not possible (meaning there are local commits that the remote branch doesn't have), Git performs a "merge commit," which creates a new commit to merge the divergent histories.

2. **Introduction of Warning in Git 2.27:**

   - In Git version 2.27 and later, a change was introduced to provide a warning if the `pull.rebase` configuration variable is not set. This warning will be shown when you use `git pull`.

3. **The `pull.rebase` Configuration Variable:**

   - The `pull.rebase` configuration variable controls the default behavior of `git pull` when it comes to rebasing versus merging.
     Helpful video
     https://youtu.be/0chZFIZLR_0
   - "Rebasing" involves moving or replaying your local commits on top of the fetched remote commits, resulting in a linear history even when integrating changes from a divergent branch.
   - "Merging" involves creating a new merge commit to combine divergent histories, which might result in a more complex history.

4. **Setting the `pull.rebase` Variable:**

   - To maintain the default behavior of Git (fast-forward if possible, else create a merge commit), you can set `pull.rebase` to "false" globally using this command: `git config --global pull.rebase "false"`.
   - This means that if you don't specify whether to rebase or merge, Git will use the default behavior of creating a merge commit when necessary.

5. **Choosing Rebase When Pulling:**

   - If you prefer to use rebasing when pulling changes, you can set `pull.rebase` to "true" globally: `git config --global pull.rebase "true"`.
   - This means that when you run `git pull`, Git will attempt to rebase your local changes on top of the fetched changes, resulting in a more linear history.

6. **Effect of the Configuration:**
   - Once the `pull.rebase` variable is set, Git will follow the specified behavior for all future `git pull` commands until the configuration is changed.

In summary, the explanation clarifies how the `git pull` command's behavior regarding rebasing and merging has been affected by the `pull.rebase` configuration variable in Git version 2.27 and later. Users can now choose the default behavior they prefer by setting this variable accordingly.

#### Fast forward merge and merge commit

Sure, let's break down those explanations with examples:

**1. Fast-Forward Merge:**
Imagine you have a simple scenario with a local branch named `feature` and a remote branch named `origin/feature`.

```
A - B - C (origin/feature)
     \
      D - E (feature, your local branch)
```

In this scenario:

- Commits A, B, and C are on the remote branch.
- You've made local commits D and E on your local branch.

When you run `git pull` without specifying any options, and your local branch has not diverged from the remote branch (no new local commits), Git will perform a fast-forward merge:

```
A - B - C (origin/feature)
         \
          D - E (feature, your local branch)
```

Here, Git simply moves the pointer of your local branch forward to match the pointer of the remote branch. This results in a linear history, where the remote commits are integrated into your local branch without creating any new merge commits.

**2. Merge Commit (Diverged Histories):**
Now, consider a scenario where your local branch has diverged from the remote branch:

```
A - B - C (origin/feature)
     \
      D - E (feature, your local branch)
```

Here:

- Commits A, B, and C are on the remote branch.
- Your local branch has additional commits D and E.

When you run `git pull`, and your local branch has new commits that the remote branch doesn't have, Git will perform a merge commit:

```
A - B - C (origin/feature)
     \   \
      D - E - M (feature, your local branch)
```

In this case, Git creates a new merge commit `M` that combines the histories of both branches. This merge commit has two parent commits, E (your latest commit) and C (the latest commit on the remote branch). This creates a branching point in the history, showing where the two histories were combined.

So, in summary:

- Fast-forward merge happens when your local branch has no new commits compared to the remote branch. The local branch pointer moves forward, and the history remains linear.
- Merge commit happens when your local branch has new commits that the remote branch doesn't have. A new commit is created to merge the histories, resulting in a branching point.

The choice between these two approaches depends on your workflow and the desired history structure.

### Pushing to your remotes

#### Some important terms

In the context of version control systems like Git, "upstream" refers to the original or main repository from which you cloned your own repository. When you fork a repository on platforms like GitHub or GitLab, you create a copy of the repository under your own account. The original repository from which you forked is considered the "upstream" repository.

Here's what the term "upstream" means and how it's relevant to sharing your project:

1. **Upstream Repository:** The upstream repository is the primary or source repository that serves as the authoritative version of the codebase. It's the repository that others may contribute to, and it typically represents the main development branch of a project.

2. **Your Fork (Origin):** When you want to contribute to a project, you often start by creating your own copy of the upstream repository. This is called a "fork." The forked repository becomes your "origin" repository. You clone your origin repository to your local machine, make changes, and then push those changes back to your origin repository.

3. **Sharing Changes:** Once you've made changes to your origin repository and you want to contribute those changes back to the main project, you need to share them with the upstream repository. This is where the term "pushing upstream" comes in.

   - **Pushing Upstream:** Pushing upstream means sending your changes from your origin repository back to the original repository (the upstream repository) so that they can be reviewed and potentially integrated into the main project.

   - **Creating a Pull Request:** On platforms like GitHub, you typically initiate this process by creating a "pull request" (or merge request in other systems). This is a request to the maintainers of the upstream repository to consider your changes for inclusion.

   - **Code Review and Integration:** The maintainers of the upstream repository review your changes, provide feedback, and decide whether to merge your changes into the main project.

So, the term "pushing upstream" means sharing your changes from your forked repository back to the original repository. It's a key concept in open-source collaboration and version control systems, as it allows contributors to contribute their work to the larger project.

#### CONTD.

When you have your project at a point that you want to share, you have to push it upstream. The command for this is simple: git push `<remote> <branch>`. If you want to push your master branch to your origin server (again, cloning generally sets up both of those names for you automatically), then you can run this to push any commits you’ve done back up to the server:

This command works only if you cloned from a server to which you have write access and if
nobody has pushed in the meantime. If you and someone else clone at the same time and they push upstream and then you push upstream, your push will rightly be rejected. You’ll have to fetch their work first and incorporate it into yours before you’ll be allowed to push.

#### Inspecting a remote

If you want to see more information about a particular remote, you can use the git remote show `<remote>` command. If you run this command with a particular shortname, such as origin, you get something like this:

```
$ git remote show origin
* remote origin
Fetch URL: https://github.com/schacon/ticgit
Push URL: https://github.com/schacon/ticgit
HEAD branch: master
Remote branches:
master tracked
dev-branch tracked
Local branch configured for 'git pull':
master merges with remote master
Local ref configured for 'git push':
master pushes to master (up to date)
```

#### Renaming and removing remotes

You can run git remote rename to change a remote’s shortname. For instance, if you want to rename pb to paul, you can do so with git remote rename:

```
$ git remote rename pb paul
$ git remote
origin
paul
```

It’s worth mentioning that this changes all your remote-tracking branch names, too. What used to be referenced at pb/master is now at paul/master.
If you want to remove a remote for some reason — you’ve moved the server or are no longer using a particular mirror, or perhaps a contributor isn’t contributing anymore — you can either use git remote remove or git remote rm:

```
$ git remote remove paul
$ git remote
origin
```

### Tagging

Listing the existing tags in Git is straightforward. Just type git tag (with optional -l or --list):

```
$ git tag
v1.0
v2.0
```

This command lists the tags in alphabetical order; the order in which they are displayed has no real importance.
You can also search for tags that match a particular pattern. The Git source repo, for instance, contains more than 500 tags. If you’re interested only in looking at the 1.8.5 series, you can run this:

```
$ git tag -l "v1.8.5*"
v1.8.5
v1.8.5-rc0
v1.8.5-rc1
v1.8.5-rc2
v1.8.5-rc3
v1.8.5.1
v1.8.5.2
v1.8.5.3
v1.8.5.4
v1.8.5.5
```

### Creating tags

Git supports two types of tags: lightweight and annotated.
A lightweight tag is very much like a branch that doesn’t change — it’s just a pointer to a specific commit. Annotated tags, however, are stored as full objects in the Git database. They’re checksummed;

contain the tagger name, email, and date; have a tagging message; and can be signed and verified with GNU Privacy Guard (GPG). It’s generally recommended that you create annotated tags so you can have all this information; but if you want a temporary tag or for some reason don’t want to keep the other information, lightweight tags are available too.

Creating an annotated tag in Git is simple. The easiest way is to specify -a when you run the tag
command:

```
$ git tag -a v1.4 -m "my version 1.4"
$ git tag
v0.1
v1.3
v1.4
```

The -m specifies a tagging message, which is stored with the tag. If you don’t specify a message for an annotated tag, Git launches your editor so you can type it in.

You can see the tag data along with the commit that was tagged by using the git show command:

```
$ git show v1.4
tag v1.4
Tagger: Ben Straub <ben@straub.cc>
Date: Sat May 3 20:19:12 2014 -0700
my version 1.4
commit ca82a6dff817ec66f44342007202690a93763949
Author: Scott Chacon <schacon@gee-mail.com>
Date: Mon Mar 17 21:52:11 2008 -0700
Change version number
```

##### Light weight tags

Another way to tag commits is with a lightweight tag. This is basically the commit checksum stored
in a file — no other information is kept. To create a lightweight tag, don’t supply any of the -a, -s, or -m options, just provide a tag name:

```
$ git tag v1.4-lw
$ git tag
v0.1
v1.3
v1.4
v1.4-lw
v1.5
```

This time, if you run git show on the tag, you don’t see the extra tag information. The command just shows the commit:

```
$ git show v1.4-lw
commit ca82a6dff817ec66f44342007202690a93763949
Author: Scott Chacon <schacon@gee-mail.com>
Date: Mon Mar 17 21:52:11 2008 -0700
Change version number
```

#### Tagging later

You can also tag commits after you’ve moved past them. Suppose your commit history looks like this:

```
$ git log --pretty=oneline
15027957951b64cf874c3557a0f3547bd83b3ff6 Merge branch 'experiment'
a6b4c97498bd301d84096da251c98a07c7723e65 Create write support
0d52aaab4479697da7686c15f77a3d64d9165190 One more thing
6d52a271eda8725415634dd79daabbc4d9b6008e Merge branch 'experiment'
0b7434d86859cc7b8c3d5e1dddfed66ff742fcbc Add commit function
4682c3261057305bdd616e23b64b0857d832627b Add todo file
166ae0c4d3f420721acbb115cc33848dfcc2121a Create write support
9fceb02d0ae598e95dc970b74767f19372d61af8 Update rakefile
964f16d36dfccde844893cac5b347e7b3d44abbc Commit the todo
8a5cbc430f1a9c3d00faaeffd07798508422908a Update readme
```

Now, suppose you forgot to tag the project at v1.2, which was at the “Update rakefile” commit. You can add it after the fact. To tag that commit, you specify the commit checksum (or part of it) at the end of the command:

```
$ git tag -a v1.2 9fceb02
```

### Alias in git

```
$ git config --global alias.co checkout
$ git config --global alias.br branch
$ git config --global alias.ci commit
$ git config --global alias.st status
```

This means that, for example, instead of typing git commit, you just need
to type git ci. As you go on using Git, you’ll probably use other commands
frequently as well; don’t hesitate to create new aliases.
This technique can also be very useful in creating commands that you think
should exist. For example, to correct the usability problem you encountered
with unstaging a file, you can add your own unstage alias to Git:

```
$ git config --global alias.unstage 'reset HEAD --'
```

This makes the following two commands equivalent:

```
$ git unstage fileA
$ git reset HEAD -- fileA
```

This seems a bit clearer. It’s also common to add a last command, like this:

```
$ git config --global alias.last 'log -1 HEAD'
```

This way, you can see the last commit easily:

```
$ git last
commit 66938dae3329c7aebe598c2246a8e6af90d04646
Author: Josh Goebel <dreamer3@example.com>
Date:
Tue Aug 26 19:48:51 2008 +0800
test for current head
```

# Git Branching

Branching means you diverge from the main line of development and continue to do work without messing with that main line.

## Intro

Git doesn’t store data as a series of
changesets or differences, but instead as a series of snapshots.
When you make a commit, Git stores a commit object that contains a pointer
to the snapshot of the content you staged. This object also contains the au-
thor’s name and email, the message that you typed, and pointers to the commit
or commits that directly came before this commit (its parent or parents): zero
parents for the initial commit, one parent for a normal commit, and multiple
parents for a commit that results from a merge of two or more branches.

The process you described outlines how Git stores data in a repository and the relationships between different types of objects in Git, such as blobs, trees, and commits. Let's break down each step and explain it in more detail:

1. **Staging Files**: When you run `git add` for each file (e.g., README, test.rb, LICENSE), Git stages these files for commit. Staging essentially means that you're telling Git to include the changes in these files in the next commit. When you stage a file, Git calculates the SHA-1 hash (checksum) of the file's contents. This hash serves as a unique identifier for the file's content.

2. **Creating Blobs**: After you've staged the files, Git creates a blob object for each file. A blob is simply a data object that stores the content of a file. These blobs are stored in the Git repository, and their filenames are represented by the SHA-1 hashes of their contents. Git uses these blobs to efficiently store and manage file content. So in your case, you have three blob objects, each containing the content of one of your files.

3. **Creating a Tree Object**: Git doesn't store files directly in a commit; instead, it uses tree objects to represent directory structures. When you commit, Git calculates a tree object that represents the state of your entire project directory at that point in time. This tree object contains pointers to the blob objects that correspond to the files in your project. It also stores the file names and permissions.

4. **Creating a Commit Object**: Once the tree object is created, Git creates a commit object. A commit object contains metadata such as the commit message, author information, timestamp, and a pointer to the root tree object that represents your project's directory structure. In your case, this commit object represents the initial state of your project, and it includes a reference to the tree object that describes the state of your files and directories at that moment.

So, after running `git commit`, your Git repository contains the following five objects:

1. Three blob objects, each storing the content of one of your files.
2. One tree object representing the root directory and pointing to the blobs for your files.
3. One commit object that contains metadata (like your commit message) and a reference to the root tree object.

These objects collectively form a snapshot of your project's state at the time of the commit. Git's history is built by linking these commit objects together in a chain, with each commit pointing to its parent commit, forming a version history of your project. This allows Git to efficiently track changes over time and recreate any previous snapshot of your project if needed.
![](../../../statics/Pasted%20image%2020231001121804.png)

If you make some changes and commit again, the next commit stores a
pointer to the commit that came immediately before it.

![](../../../statics/Pasted%20image%2020231001121853.png)

A branch in Git is simply a lightweight movable pointer to one of these com-
mits. The default branch name in Git is master. As you start making commits,
you’re given a master branch that points to the last commit you made. Every
time you commit, it moves forward automatically.

![](../../../statics/Pasted%20image%2020231001122020.png)

### Creating a branch

What happens if you create a new branch? Well, doing so creates a new pointer
for you to move around. Let’s say you create a new branch called testing. You
do this with the git branch command:

```
$ git branch testing
```

This creates a new pointer to the same commit you’re currently on.

![](../../../statics/Pasted%20image%2020231001122150.png)
How does Git know what branch you’re currently on? It keeps a special
pointer called HEAD.
In Git, this is a pointer to the local branch you’re currently on. In this case, you’re still on master.
The git branch command only created a new branch – it didn’t switch to that
branch.

![](../../../statics/Pasted%20image%2020231001122304.png)

You can easily see this by running a simple git log command that shows
you where the branch pointers are pointing. This option is called --decorate.

```
$ git log --oneline --decorate
f30ab (HEAD -> master, testing) add feature #32 - ability to add new formats to the central
34ac2 Fixed bug #1328 - stack overflow under certain conditions
98ca9 The initial commit of my project
```

You can see the “master” and “testing” branches that are right there next to
the f30ab commit.

### Switching branch

To switch to an existing branch, you run the git checkout command. Let’s
switch to the new testing branch:

```
$ git checkout testing
```

This moves HEAD to point to the testing branch.

![](../../../statics/Pasted%20image%2020231001122527.png)

What is the significance of that? Well, let’s do another commit:

```
$ vim test.rb
$ git commit -a -m 'made a change'
```

![](../../../statics/Pasted%20image%2020231001122648.png)
This is interesting, because now your testing branch has moved forward,
but your master branch still points to the commit you were on when you ran
git checkout to switch branches. Let’s switch back to the master branch:

![](../../../statics/Pasted%20image%2020231001122714.png)

That command did two things. It moved the HEAD pointer back to point to
the master branch, and it reverted the files in your working directory back to
the snapshot that master points to. This also means the changes you make
from this point forward will diverge from an older version of the project. It es-
sentially rewinds the work you’ve done in your testing branch so you can go
in a different direction.

_It’s important to note that when you switch branches in Git, files in your
working directory will change. If you switch to an older branch, your
working directory will be reverted to look like it did the last time you
committed on that branch. If Git cannot do it cleanly, it will not let you
switch at all_

![](../../../statics/Pasted%20image%2020231001122910.png)

You can also see this easily with the git log command. If you run git log
--oneline --decorate --graph --all it will print out the history of your
commits, showing where your branch pointers are and how your history has di-
verged

```
$ git log --oneline --decorate --graph --all
* c2b9e (HEAD, master) made other changes
| * 87ab2 (testing) made a change
|/
* f30ab add feature #32 - ability to add new formats to the
* 34ac2 fixed bug #1328 - stack overflow under certain conditions
* 98ca9 initial commit of my project
```

a branch in Git is in actuality a simple file that contains the 40 char-
acter SHA-1 checksum of the commit it points to, branches are cheap to create
and destroy. Creating a new branch is as quick and simple as writing 41 bytes to
a file (40 characters and a newline).

### Basic Branching

To create a branch and switch to it at the
same time, you can run the git checkout command with the -b switch:

```
$ git checkout -b iss53
```

Switched to a new branch "iss53"
This is shorthand for:

```
$ git branch iss53
$ git checkout iss53
```

You work on your web site and do some commits. Doing so moves the iss53
branch forward, because you have it checked out (that is, your HEAD is pointing
to it):
![](../../../statics/Pasted%20image%2020231001123441.png)

However, before you do that, note that if your working directory or staging
area has uncommitted changes that conflict with the branch you’re checking
out, Git won’t let you switch branches. It’s best to have a clean working state
when you switch branches

This
is an important point to remember: when you switch branches, Git resets your
working directory to look like it did the last time you committed on that branch.
It adds, removes, and modifies files automatically to make sure your working
copy is what the branch looked like on your last commit to it.

Next, you have a hotfix to make. Let’s create a hotfix branch on which to
work until it’s completed:

```
$ git checkout -b hotfix
Switched to a new branch 'hotfix'
$ vim index.html
$ git commit -a -m 'fixed the broken email address'
```

![](../../../statics/Pasted%20image%2020231001123712.png)

You can run your tests, make sure the hotfix is what you want, and merge it
back into your master branch to deploy to production. You do this with the git
merge command:

```
$ git checkout master
$ git merge hotfix
Updating f42c576..3a0874c
Fast-forward
index.html | 2 ++
1 file changed, 2 insertions(+)
```

You’ll notice the phrase “fast-forward” in that merge. Because the commit C4
pointed to by the branch hotfix you merged in was directly ahead of the com-
mit C2 you’re on, Git simply moves the pointer forward. To phrase that another
way, when you try to merge one commit with a commit that can be reached by
following the first commit’s history, Git simplifies things by moving the pointer
forward because there is no divergent work to merge together – this is called a
“fast-forward.”

![](../../../statics/Pasted%20image%2020231001123923.png)

After your super-important fix is deployed, you’re ready to switch back to the
work you were doing before you were interrupted. However, first you’ll delete
the hotfix branch, because you no longer need it – the master branch points
at the same place. You can delete it with the -d option to git branch:

```
$ git branch -d hotfix
Deleted branch hotfix (3a0874c).
```

![](../../../statics/Pasted%20image%2020231001124035.png)

### Basic Merging

you’ll merge your iss53 branch into master, much like you merged your hotfix branch earlier. All you have to do is check out the branch you wish to merge into and then run the git
merge command:

```
$ git checkout master
Switched to branch 'master'
$ git merge iss53
Merge made by the 'recursive' strategy.
index.html |
1 +
1 file changed, 1 insertion(+)
```

This looks a bit different than the hotfix merge you did earlier. In this case,
your development history has diverged from some older point. Because the
commit on the branch you’re on isn’t a direct ancestor of the branch you’re
merging in, Git has to do some work. In this case, Git does a simple three-way
merge, using the two snapshots pointed to by the branch tips and the common
ancestor of the two
![](../../../statics/Pasted%20image%2020231001124833.png)
Instead of just moving the branch pointer forward, Git creates a new snap-
shot that results from this three-way merge and automatically creates a new
commit that points to it. This is referred to as a merge commit, and is special in
that it has more than one parent.

![](../../../statics/Pasted%20image%2020231001124918.png)
It’s worth pointing out that Git determines the best common ancestor to use
for its merge base;

### Basic merge conflicts

If you changed the same part of
the same file differently in the two branches you’re merging together, Git won’t
be able to merge them cleanly. If your fix for issue #53 modified the same part
of a file as the hotfix, you’ll get a merge conflict that looks something like this:

```
$ git merge iss53
Auto-merging index.html
CONFLICT (content): Merge conflict in index.html
Automatic merge failed; fix conflicts and then commit the result.
```

Git hasn’t automatically created a new merge commit. It has paused the pro-
cess while you resolve the conflict. If you want to see which files are unmerged
at any point after a merge conflict, you can run git status:

```
$ git status
On branch master
You have unmerged paths.
(fix conflicts and run "git commit")
Unmerged paths:
(use "git add <file>..." to mark resolution)
both modified:
index.html
no changes added to commit (use "git add" and/or "git commit -a")
```

Anything that has merge conflicts and hasn’t been resolved is listed as un-
merged. Git adds standard conflict-resolution markers to the files that have
conflicts, so you can open them manually and resolve those conflicts. Your file
contains a section that looks something like this:

```
<<<<<<< HEAD:index.html
<div id="footer">contact : email.support@github.com</div>
=======
<div id="footer">
please contact us at support@github.com
</div>
>>>>>>> iss53:index.html
```

This means the version in HEAD (your master branch, because that was what
you had checked out when you ran your merge command) is the top part of
that block (everything above the `=======`), while the version in your iss53
branch looks like everything in the bottom part. In order to resolve the conflict,
you have to either choose one side or the other or merge the contents yourself.
For instance, you might resolve this conflict by replacing the entire block with
this:
After you’ve resolved each of
these sections in each conflicted file, run git add on each file to mark it as re-
solved. Staging the file marks it as resolved in Git

If you want to use a graphical tool to resolve these issues, you can run git
mergetool, which fires up an appropriate visual merge tool and walks you
through the conflicts:

```
$ git mergetool
This message is displayed because 'merge.tool' is not configured.
See 'git mergetool --tool-help' or 'git help config' for more details.
'git mergetool' will now attempt to use one of the following tools:
opendiff kdiff3 tkdiff xxdiff meld tortoisemerge gvimdiff diffuse diffmerge ecmerge p4merge
Merging:
index.html
Normal merge conflict for 'index.html':
{local}: modified file
{remote}: modified file
Hit return to start merge resolution tool (opendiff):
```

After you exit the merge tool, Git asks you if the merge was successful. If you
tell the script that it was, it stages the file to mark it as resolved for you. You can
run git status again to verify that all conflicts have been resolved:

```
$ git status
On branch master
All conflicts fixed but you are still merging.
(use "git commit" to conclude merge)
Changes to be committed:
modified:
index.html
```

If you’re happy with that, and you verify that everything that had conflicts
has been staged, you can type git commit to finalize the merge commit. The
commit message by default looks something like this:
