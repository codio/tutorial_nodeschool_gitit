@annotation:tour get_git
#1. Get Git
Git is **open source software** (free for anyone to use) written by Linus Torvalds who also wrote the Linux operating system. 

It is a program for keeping track of changes over time, known in programming as **version control**.

##Git is preinstalled on Codio
Git is already preinstalled on Codio, so there is nothing you need to do.  
  
Git isn't like other programs on your computer. You'll likely not see an icon on your desktop, but it will always be available to you and you'll be able to access it at anytime from you're terminal (which you're in right now!) or Git desktop applications.
  
Once it is installed, open terminal (aka Bash, aka Shell, aka Prompt). You can verify that it's really there by typing:
  
    $ git --version
  
This will return the version of Git that you're running.
  
Next, configure Git so it knows who to associate your changes to:

##Setting Global Stuff
The following steps do not need to be done with Codio as your details are taken from Codio if you sign in with GitHub.

For completeness, here are the instructions if you are not signed into Codio with GitHub.

Set your name:
  
    $ git config --global user.name "Your Name"
  
Now set your email:

    $ git config --global user.email youremail@example.com

When you're done type into terminal:

    $ git-it
   
To open the lesson menu. Select the lesson you are running and <Enter> and then

    $ git-it verify

**PRO TIP**: Dollar signs are often used in programming documentation to signify that the line is command line code. You don't actually type it in, though, only type `git-it verify`.
  
When you finish each challenge, type `git-it` to see the menu and go to the next challenge. Some of the challenges are longer than the screen, so don't forget to scroll up to where it begins after it loads!


@annotation:tour repository
#2. Repository
##Challenge
A **repository** is essentially a project. You can imagine it as project's folder with all the related files inside of it. In fact, that's what it will look like on your computer anyways.

You tell Git what your project is and Git will start tracking all of the changes to that folder. Files added or subtracted or even a single letter in a single file added -- all of it's tracked and time stamped by Git.
  
###Create a Repository
You're going to create a new folder and initialize it as a Git repository. You'll need some basic terminal (Bash) commands (see below) for moving around and creating folders (just like you'd do in Finder or Windows Explorer). 
  
To make things easier, name your folder what you'd name the project, keep it lowercase, no spaces or symbols. How about 'sandwich'.
  
You can type all of this here in your terminal window.
  
To make a new folder:
  
    $ mkdir sandwich
  
To go into that folder:
  
    $ cd sandwich
  
To create a new Git instance for a project:

    $ git init

That's it! It will just return you to a new line.
  
When you've initialized a new Git repository, run:

    $ git-it
   
To open the lesson menu. Select the lesson you are running and <Enter> and then

    $ git-it verify
  
  
###TERMINAL TIPS
Make a new folder (aka directory)

    $ mkdir <FOLDERNAME>

Navigate into an existing folder (aka change directory)

    $ cd <FOLDERNAME>

List the items in a folder

    $ ls 
  
Turn Git on for a folder

    $ git init

@annotation:tour commit_to_it 
#3. Commit to It
##Challenge
Create a file in your new repository, add something to that file and commit those changes to Git.

Now that you've got a repository started, add a file to it. 
  
##New File
Open a text editor. Now write a couple of lines of text, perhaps describe the tastiest sandwich you can imagine, and save the file in the folder you created in the last lesson.

##Check, Add and Commit Changes
Next check the **status** of your repository. Below in this terminal, you should still be within the new folder you created. See if there are changes listed:
  
    $ git status

Then **add** the file you just created to the files you'd like to **commit** (aka save) to change (for instance, if your file is named readme.md, `git add readme.md`). 
  
    $ git add <FILENAME>

Finally, **commit** those changes to the repository's history with a short description of the updates. See the command hints below!
  
    $ git commit -m "your commit message"
  
###Make More Changes  
Now add another line to your .txt file, perhaps a title, and save.
  
In terminal, you can view the **diff**erence between the file now and how it was at your last commit. 
  
    $ git diff
  
Now with what you just learned above, commit this latest change.
  
When all changes are committed, 

    $ git-it
   
To open the lesson menu. Select the lesson you are running and <Enter> and then

    $ git-it verify
  
##Git Tips
Check status of changes to a repository

    $ git status
  
View changes to files

    $ git diff

Add a file's changes to be commited

    $ git add <FILENAME>

To add all files' changes

    $ git add .

To commit (aka save) the changes you've added with a short message describing the changes

    $ git commit -m "your commit message"


@annotation:tour githubbin
#4. Githubbin
##Challenge
The repository you've created so far is just on your computer, which is handy, but makes it pretty hard to share and work with others on. No worries, that's what GitHub.com is for! In this challenge, get Git and GitHub configured.

##Create a GitHub Account
GitHub is a website that allows people everywhere to share what they're working on with Git and to easily work together.

  - Visit **http://www.github.com** and sign up for a free account.
  - High five, welcome!

##Configure Git
You can also add your GitHub username to your Git configuration, which will be needed in order to verify the upcoming challenges:

Add your GitHub username to your configuration:
  
    $ git config --global user.username githubusername

When you've set everything up, 

    $ git-it
   
To open the lesson menu. Select the lesson you are running and <Enter> and then

    $ git-it verify


@annotation:tour remote_control
#5. Remote Control
##Challenge
Connect your local and remote repositories and push changes.

GitHub.com stores a **remote** copy of your repository (it's 'remote' because that copy is not on your computer, but on a server elsewhere). By **pushing your **local** (on your computer) changes to it, you keep it up to date. That way others can always get the latest, too. And everyone can work on a project together without needing access to your computer where your local copy is stored.

##Create a Remote Repository
You want to sync your **local** version with one stored on GitHub.com called the remote version. 

So first create an empty remote repository on GitHub.com.

  - Go to [www.github.com](http://github.com), log in, and click the '+' in the top right to
  create a new repository.
  - Give it a name that matches your local repository's name and a short description.
  - Make it public.
  - Don't initialize with a README
  - Leave .gitignore and license on 'none'.
  - Click create repository!

##Readmes, .gitignores and Licenses
These are common files in open source projects. 

- A **readme** explains what the project is, how to use it, and often times, how to contribute (though sometimes there is an extra file, `CONTRIBUTING.md`, for those details). 
- A **.gitignore** is a list of files that Git should *not* track (for instance, files with passwords!). 
- A **license** file is the type of license you put on your project, information on the types can be found at [www.choosealicense.com](www.choosealicense.com). 

We don't need them, however, for this example.

##Connect your Local to your Remote
Now you've got an empty repository started on GitHub.com. At the top you'll see 'Quick Setup', make sure the 'HTTP' button is selected and copy the address - this is the location of your repository on GitHub.

Back in your terminal, and inside of the folder that you initialized as a Git repository in the previous challenge, you want to tell Git the location of the remote version. This is commonly named `origin`.

    $ git remote add origin <URLFROMGITHUB>

A note:

If you have GitHub for Windows on your computer, a remote named 'origin' is automatically created. In that case, you'll just need to tell it what URL to associate with origin. Use this command instead of the 'add' one above:

    $ git remote set-url origin <URLFROMGITHUB>

Your **local** version is now connected to the **remote** on GitHub.com.

##Push Work to your Remote

Next you want to **push** everything you've done locally to GitHub.

Git has a branching system so that you can work on different parts of a project at different times. By default the first branch is named master. When you push (and later pull) from a project, you tell Git the branch name you want and the name of the remote that it lives on.

    $ git push origin master

For a visual on how branches work in a project, see this GitHub Guide: [guides.github.com/overviews/flow/](http://guides.github.com/overviews/flow/) 

Now go to GitHub and refresh the page of your repository. WOAH! Everything is the same locally and remotely. Congrats on your first public repository!

When you're synced locally and on GitHub.com, run:

    $ git-it
   
To open the lesson menu. Select the lesson you are running and <Enter> and then

    $ git-it verify

##GIT TIPS
Add remote connections

    $ git remote add <REMOTENAME> <URL>

Set a URL to a remote

    $ git remote set-url <REMOTENAME> <URL>

Pull in changes

    $ git pull <REMOTENAME> <BRANCHNAME>

View remote connections

    $ git remote -v

Push changes

    $ git push <REMOTENAME> <BRANCH>



@annotation:tour forks_and_clones
#6. Forks and Clones
##Challenge
Fork a project from GitHub.com and clone it locally.
  
Now you've made a project locally and pushed it to GitHub, but that's only half the fun. The other half is working with other people and projects.

When you **fork** a repository, you're creating a copy of it on your GitHub.com account. Forks are used for creating your own version of a project or contributing back fixes or features to the original project. 
  
Once a project is forked, you then **clone** (aka copy) it from GitHub to your computer to work on locally.

##Fork
The project we'll work with is **www.github.com/jlord/patchwork**. Go to that site and click the fork button at the top right. Once the fork animation is complete, you've got a copy on your account. Copy your fork's HTTP URL on the right side.
  
##Clone a Repository
Now, in terminal, clone the repository. It will create a new folder for the repository so no need to create one. But make sure you aren't cloning it inside of another Git repository folder! So, if you're still inside of the repository you created in the early challenges, back out of that folder: `cd ..`

    $ git clone <URL>

Navigate into that folder (in this case, named 'patchwork')

    $ cd patchwork

Now you've got a copy of the repository on your computer and it is automatically connected to the remote repository (your forked copy) on your GitHub account.

##Connect to the Original Repository
But what if the original repository you forked changes? You'll want to be able to **pull** in those changes too. So let's add a remote connection to the original, **github.com/jlord/patchwork**, repository with its URL, found on the right hand side of the original on GitHub.

You can name this remote connection anything you want, but often people use 'upstream', let's use that for this. 

    $ git remote add upstream https://github.com/jlord/patchwork.git
  
When you've done these steps, 

    $ git-it
   
To open the lesson menu. Select the lesson you are running and <Enter> and then

    $ git-it verify
  
##GIT TIPS
Add remote connections

    $ git remote add <REMOTENAME> <URL>
  
View remote connections

    $ git remote -v


@annotation:tour branches_arent_just_for_birds
#7. Branches aren't just for birds
##Challenge
Create a new branch for your contribution.

Git repositories use branches to isolate work when needed. It's common practice when working on a project or with others on a project to create a **branch** to put your changes in. This way you can do your work while the main, commonly named 'master', branch stays stable.

##GitHub Pages
GitHub.com will automatically serve and host static website files in branches named 'gh-pages'. Since the project you forked creates a website, its main branch is 'gh-pages'. All sites like this can be found using this pattern for the URL: 

  http://githubusername.github.io/repositoryname

##Create a branch
When you create a branch, Git copies everything from the current branch you're on and places it in the branch you've requested.

Type `git status` to see what branch you're currently on (it should be `gh-pages`)

Create a branch and name it "add-<username>", where 'username' is your username. For instance, "add-jlord". 

    $ git branch <BRANCHNAME>

Now you have a branch with a new name identical to 'gh-pages'.

To go into that branch and work on it, similar to using `cd` to change directory in terminal, you **checkout** a branch.

    $ git checkout <BRANCHNAME>

##Create a new file
Back to the text editor. In the 'contributors' folder, create a new file named "add-<username>.txt", where 'username' is your username. For instance, "add-jlord.txt". Then, just write your GitHub username in it, that's it and that's all. For instance, I'd type 'jlord' and hit save.  

##Check-in
Go through the steps for checking in a project: 

    $ git status
    $ git add <filename>
    $ git commit -m "commit message"

Now push your update to your fork on GitHub:

    $ git push origin <BRANCHNAME>
    
When you have done, type into terminal:

    $ git-it

To open the lesson menu. Select the lesson you are running and <Enter> and then

    $ git-it verify

##GIT TIPS

You can create and switch to a branch in one line:

    $ git checkout -b <BRANCHNAME>

Create a new branch:

    $ git branch <BRANCHNAME>

Move onto a branch:

    $ git checkout <BRANCHNAME>

List the branches:

    $ git branch

Rename a branch you're currently on:

    $ git branch -m <NEWBRANCHNAME>

Verify what branch you're working on

    $ git status


@annotation:tour its_a_small_world
#8. It's a small world
##Challenge
Add a collaborator.

Working with others is one of the best things about GitHub because it makes it easy to work from all over the world at any time.

###Collaborators
**Collaborators** are other GitHub users who are given permission to make edits to a repository owned by someone else. To add **collaborators** to a project, visit the repository's GitHub page 
and click the 'Settings' icon on the right side menu. Then select the 'Collaborators' tab. Type in the username to add and click 'Add'.

##Hello, Repo Robot!
Go to the your forked Patchwork repository's page on GitHub and add 'reporobot' as a collaborator.

    http://www.github.com/yourusername/patchwork

When you've added Reporobot as a collaborator to your repo, type into terminal:

    $ git-it
   
To open the lesson menu. Select the lesson you are running and <Enter> and then

    $ git-it verify

##GIT TIPS
Pull in changes from a remote

    $ git pull <REMOTENAME> <BRANCH>

Copy a repository to your computer

    $ git clone <URL>

Add remote connections

    $ git remote add <REMOTENAME> <URL>

View remote connections

    $ git remote -v


@annotation:tour pull_never_out_of_date
#9. Pull never out of date
##Challenge
Keep your file up to date, pull in changes from collaborators.

If you're working on something with someone you need to stay up to date with the latest version. So you'll want to **pull** in any changes that may have been made.

##Pull in Changes
See if Reporobot has made any changes to your 'add-' branch by pulling in from the remote named 'origin' on GitHub:

    $ git pull <REMOTENAME> <BRANCHNAME>

If nothing's changed, it will tell you 'Already up-to-date'. If there are changes, it will merge those changes into your local version.

Did Reporobot make changes? Git tells you where changes were made. You can open that file and see Reporobot's updates. Surprise, Reporobot is an artist!

When you're done type into terminal:

    $ git-it
   
To open the lesson menu. Select the lesson you are running and <Enter> and then

    $ git-it verify

##GIT TIPS
Check Git status

    $ git status

Pull in changes from a remote branch

    $ git pull <REMOTENAME> <REMOTEBRANCH>

See changes to the remote before you pull in

    $ git fetch --dry-run


@annotation:tour requesting_you_pull_please
#10. Requesting you pull please
##Challenge
Submit a Pull Request.

When you make changes and improvements to a project you've forked, often you'll want to (and have intended to from the get-go) send those changes to the maintainer of the original and **request** that they **pull** the changes into the original so that everyone can benefit from the updates - that's a **pull request**.

We want to add you to the list of workshop finishers, so make a **pull request** to the original: **www.github.com/jlord/patchwork**.

##Create a pull request

- visit the original repository you forked on GitHub, in this case **http://www.github.com/jlord/patchwork**

Often GitHub will detect if you've pushed a branch to a fork and display it at the top of the original's website. If you see that, you can click Create Pull Request. If not:

- Click 'Pull request' on the right-side menu, then 'New pull request'.
- Select the branch with the changes you want to submit (it should be the one with 'add-' and your username).

You'll now see a page with the details of the pull request you're in the process of submitting. The page shows the commits and changes associated with your pull request. If the original repository has a 
contribution documentation, GitHub will link to it. 

If everything good, and as you expect it:

- click 'Create pull request'
- Add a title and description to the changes you're suggesting the original author pull in.
- click 'Send pull request'!

High five! When you've submitted your pull request, take a few seconds to bask in the moment. Then see if your pull request is merged right before your eyes! If it is, you're golden, when you're done type into terminal:

    $ git-it
   
To open the lesson menu. Select the lesson you are running and <Enter> and then

    $ git-it verify
    
If it's not merged automatically within a few moments, you'll then likely have some comments from Reporobot on why it couldn't merge it. If so, close your pull request on GitHub.com, make the necessary
changes to your branch, push those changes and resubmit your pull request.


@annotation:tour merge_tada
#11. Merge TADA
##Challenge
Merge branch, tidy up and pull upstream for much win!

Your pull request is being merged! But meanwhile, since you know that you definitely want those updates in your forked version, and your branch is in good working order, merge it into the main, branch on your forked repository, in this case, `gh-pages`.

##Merge a branch
First, move into the branch you want to merge *into* (in this case, branch `gh-pages`).

    $ git checkout <BRANCHNAME>

Now tell Git what branch you want to merge in (in this case, your feature branch that begins with "add-").

    $ git merge <BRANCHNAME>

Tidy up by deleting your feature branch now that it has been merged.

    $ git branch -D <BRANCHNAME>

You can also delete the branch from your fork on GitHub:

    $ git push <REMOTENAME> --delete <BRANCHNAME>

##Congratulations!
You've created local repositories, remote repositories, worked with a collaborator, pushed, pulled and joined the millions of others developing and enriching open source!

Visit [jlord.github.io/patchwork](http://jlord.github.io/patchwork) to see your changes incorporated!

And last but not least, if you pull in updates from the original (since it now shows you on the home page) you'll be up to date and have a version too, live at: yourusername.github.io/patchwork. 

    $ git pull upstream gh-pages

When you've merged your branch, deleted it and pulled form the original, type into terminal:

    $ git-it
   
To open the lesson menu. Select the lesson you are running and <Enter> and then

    $ git-it verify

##GIT TIPS

Merge a branch into current branch

    $ git merge <BRANCHNAME>

Change the branch you're working on

    $ git checkout <BRANCHNAME>

Delete a local branch

    $ git branch -D <BRANCHNAME>

Delete a remote branch

    $ git push <REMOTENAME> --delete <BRANCHNAME>
 
Pull from a remote branch

    $ git pull <REMOTENAME> <BRANCHNAME>

