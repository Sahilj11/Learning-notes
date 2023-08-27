## What is it 
-  it is version control tool
- Command line tool helps us keep track to changes we make to code, as we make changes to code we can create snapshot of different version. so that if something went wrong we can reference those previous version
- Helps us to synchronize code among different people
	- one version of code sort of called repository that is stored on the server
	- people can get access to this repository(same file)
	- if people make changes to those file , changes will synchronize and gets added to the repository
	- then again we can pull changes (updated repository ) from server
- allow to test changes to code without losing the original
	- once statisfied with changes , it can be merged with the original repository
	- ![[git changes.png]]
- Revert back to old version of code

## What is GIT Hub
- we need a host to put the git code somewhere , github is one of the website that provide this service
- it store git repositories

## Commands
- git clone `<url>` :- to download repository
- git add `<filename>` like `git add foo.py`:- 
	- The `git add` command is used in Git to add changes or new files to the staging area. The staging area is like a holding area where you can group changes before actually committing them to the Git repository.
	- When you make changes to your files or create new files in a Git repository, Git initially doesn't track those changes automatically. You need to explicitly tell Git which changes or files you want to include in the next commit. This is where the `git add` command comes in.
	- Here's how you can use the `git add` command:
		1. Open your terminal or command prompt and navigate to the Git repository directory.
		2. To add a specific file, you can use the command `git add <file>` where `<file>` is the name of the file you want to add. For example, if you want to add a file named "script.js," you would run `git add script.js`.		    
		3. If you want to add multiple files, you can specify their names separated by spaces. For instance, `git add file1.txt file2.txt file3.js`.		    
		4. If you want to add all the changes in the current directory and its subdirectories, you can use the command `git add .` or `git add --all`. The `.` or `--all` tells Git to add everything.    
	- After running the `git add` command, the specified changes or files are added to the staging area. This means that Git is now aware of them and ready to include them in the next commit.
	- Once you have added the necessary changes or files to the staging area using `git add`, you can then proceed to create a commit using the `git commit` command. The commit captures the changes you've added to the staging area and permanently saves them in the Git repository's history.
	- It's important to note that the `git add` command doesn't affect files that have already been committed. It only adds or updates changes that are not yet tracked or included in the staging area.
	- I hope that clarifies the usage of the `git add` command! Let me know if you have any further questions
- git commit -m "message":- git add ensure that next time you make git commit it will keep track of the previous version. message is like an comment
	- to save new snapshot of current state of repository keeping old version intact, keeping track of any of changes added using git add
	- all these changes are happening to local version of repository which we received using git clone
- git status :- used in Git to get information about the current state of your repository. It provides you with an overview of any changes you've made, the status of those changes, and other helpful information.
	- ![[status.png]]
- git push:- to update the repository online
- git commit -am "message" :- this command combine commit and add command
- git pull :- to clone the updated repository on server
- git log
- git reset:- `git reset --hard <commit>` here adding the hash of commit to go back to that commit
	- `git reset --hard origin/master`
- git branch:- tells branches present and on which branch i am currently on `*main` here main is the branch name , and * represent the branch i am currently on ^961872
	- git checkout -b style :- to check new branch(creating new branch) (style here is name of branch)
	- git checkout 'name of branch':- to switch branch
	- git merge 'name of branch you want to merge':- if you are on main branch and want to merge style branch to main then command will be `git merge style`

## Merge conflict 
- what if same code line is change in different way by different people 
- git shows this 
- ![[conflict.png]]

## Branching
- Let's imagine you're working on a story or drawing, and you want to try different ideas without messing up your original work. That's where Git branching comes in.
- In Git, a branch is like a separate copy of your project that you can work on without changing the main version. It's like making a copy of your work and saying, "I'm going to try something new here, but I won't affect the original."
- When you create a branch, you can think of it as creating a parallel universe for your project. You can make changes, add new features, fix bugs, and do whatever you want in this branch without affecting the main project or other branches.
- Let's say you're drawing a picture, and you want to try two different versions. You can create two branches: one for the first version and another for the second version. In the first branch, you can add more colors or change the background. In the second branch, you can experiment with different shapes or styles.
- Each branch keeps track of its own changes separately from the others. It's like having different "save points" for each version of your project. If you make a mistake or don't like how things are going in one branch, you can easily switch back to the original or try something else in a different branch.
- Once you're happy with the changes you've made in a branch, you can merge it back into the main project. Merging is like taking the best parts of your experiments and combining them with the original. It's like saying, "I like what I did in this branch, so let's bring those changes into the main project."
- Git makes it easy to create, switch between, and merge branches. It helps you organize your work, collaborate with others, and keep track of different ideas or versions of your project.
- Where the head is pointing is the branch that is currently been worked on
- ![[head.png]]
- git branch[[#^961872]]

## Open source contribution
- First is to fork the code :- cloning the repository to your account
- then make necessary changes to the code , there after submit pull request on open source page 

## Git Pages

## Commands
- tackling git origin already exist https://www.cloudbees.com/blog/remote-origin-already-exists-error
- .gitignore 
- 