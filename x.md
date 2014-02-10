@annotation:tour get_git
#1. Get Git
Git is **open source software** (free for anyone to use) written by Linus Torvalds who also wrote the Linux operating system. 

It is a program for keeping track of changes over time, known in programming as **version control**.

##Git is preinstalled on Codio
Git is already preinstalled on Codio, so there is nothing you need to do.  
  
Git isn't like other programs on your computer. You'll likely not see an icon on your desktop, but it will always be available to you and you'll be able to access it at anytime from you're terminal (which you're in right now!) or Git desktop applications.
  
Once it is installed, open terminal (aka Bash, aka Shell, aka Prompt). You can verify that it's really there by typing:
  
  $ git -v 
  
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
Next check the {bold}status{/bold} of your repository. Below in this terminal, you should still be within the new folder you created. See if there are changes listed:
  
  $ git status

Then {bold}add{/bold} the file you just created to the files you'd like to {bold}commit{/bold} (aka save) to change (for instance, if your file is named readme.md, `git add readme.md`). 
  
  $ git add <FILENAME>

Finally, {bold}commit{/bold} those changes to the repository's history with a short description of the updates.See the command hints below!
  
  $ git commit -m "your commit message"
  
###Make More Changes  
Now add another line to your .txt file, perhaps a title, and save.
  
In terminal, you can view the {bold}diff{/bold}erence between the file now and how it was at your last commit. 
  
  $ git diff
  
Now with what you just learned above, commit this latest change.
  
When all changes are committed, run `git-it verify`.
  
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

  $ git commit -m "your commit message"{/cyan}


@annotation:tour githubbin
#4. Githubbin
##Challenge
The repository you've created so far is just on your computer, which is handy, but makes it pretty hard to share and work with others on. No worries, that's what GitHub.com is for! In this challenge, get Git and GitHub configured.

##Create a GitHub Account
GitHub is a website that allows people everywhere to share what they're working on with Git and to easily work together.

  - Visit {bold}http://www.github.com{/bold} and sign up for a free account.
  - High five, welcome!

##Configure Git
You can also add your GitHub username to your Git configuration, which will be needed in order to verify the upcoming challenges:

Add your GitHub username to your configuration:
  
  $ git config --global user.username githubusername

When you've set everything up, run `git-it verify`


@annotation:tour remote_control
#5. Remote Control
##Challenge
Connect your local and remote repositories and push changes.

GitHub.com stores a **remote** copy of your repository (it's 'remote' because that copy is not on your computer, but on a server elsewhere). By **pushing your **local** (on your computer) changes to it, you keep it up to date. That way others can always get the latest, too. And everyone can work on a project together without needing access to your computer where your local copy is stored.

##Create a Remote Repository
You want to sync your {bold}local{/bold} version with one stored on GitHub.com called the remote version. 

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

Your {bold}local{/bold} version is now connected to the **remote** on GitHub.com.

##Push Work to your Remote

Next you want to {bold}push{/bold} everything you've done locally to GitHub.

Git has a branching system so that you can work on different parts of a project at different times. By default the first branch is named master. When you push (and later pull) from a project, you tell Git the branch name you want and the name of the remote that it lives on.

  $ git push origin master

For a visual on how branches work in a project, see this GitHub Guide: [guides.github.com/overviews/flow/](http://guides.github.com/overviews/flow/) 

Now go to GitHub and refresh the page of your repository. WOAH! Everything is the same locally and remotely. Congrats on your first public repository!

When you're synced locally and on GitHub.com, run:

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



@annotation:tour forks_and_branches
#6. Forks and Branches
##Challenge



@annotation:tour Branches aren't just for birds
#7. Branches aren't just for birds
##Challenge



@annotation:tour its_a_small_world
#8. It's a small world
##Challenge



@annotation:tour Pull never out of date
#9. Hello World
##Challenge



@annotation:tour requesting_you_pull_please
#10. Requesting you pull please
##Challenge


@annotation:tour merge_tada
#10. Merge TADA
##Challenge
