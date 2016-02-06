Set Up
------
This guide is designed to be used as a quick tutorial on Git for those new to it or anyone who just needs a refresher.  We'll cover the basics of committing, branches, and pull requests.

First, if you don't have a GitHub account yet, go to github.com and sign up for an account.  Once you're done, visit github.com/kevinzhang96/git-demo, and hit "Fork" on the top right.  This creates a copy of this repository for your own use; you'll be able to pull updates from this repository while making changes to your own copy.  Once you're done, visit your own copy.

If you haven't installed `git` yet, you can find downloads at git-scm.com/downloads.  If you install GitHub's native client at desktop.github.com, `git` will automatically be installed.  

SSH Keys
--------
Now, we'll set up an SSH key.  An SSH key allows you to secure your computer with a secret key, while using a public key to identify yourself to other devices.  Open up a terminal (Git Bash on Windows), and run `ssh-keygen`.  Follow the instructions presented; the default options are fine.  This creates a private key at `~/.ssh/id_rsa`, and a public key at `~/.ssh/id_rsa.pub`.  

Now, we want to add your public key to GitHub so that GitHub recognizes your computer and allows you to clone repositories easily.  Go back to GitHub, and click on your profile photo on the top right, then select "Settings."  On the next page, hit "SSH keys" on the left, then "New SSH key" on the right.  Back in your Terminal, type `cat ~/.ssh/id_rsa.pub | pbcopy`.  `cat ~/.ssh/id_rsa.pub` prints your public key and `| pbcopy` puts it in your clipboard.  If Terminal complains about `pbcopy`, just type `cat ~/.ssh/id_rsa.pub` and manually copy the printed text.  Back in the "New SSH key" page, give your key a name and paste your public key into the text box.  Hit "Add SSH key," and you should be all set!

Getting Started
---------------
Go back to your copy of this repository, and note the URL listed on the page (looks like `git@github.com:kevinzhang96...`).  There's a toggle on the left to pick a clone option; make sure it says SSH, and not HTTPS!  Copy this URL.  In your Terminal, `cd` into a directory that you want to store your code in; type `git clone` into your Terminal then paste the URL.  Hit enter.  After `git`'s done, you should see a new folder (type `ls`) called `git-demo`!  `cd` into it; note that it only contains a README.md file so far.  We're going to add more files and submit something called a pull request to the main repository (more on that later).

In your terminal, type `touch <your-name>.txt`, then `open .` (replace `<your-name>` with your name, of course).  You should see a folder open up on your computer; this is the `git-demo` folder!  Open up `<your-name>.txt`, and type in anything you want (let's say, something about your programming experience so far).  Save the file, and close it.  Go back into your Terminal, type `git add -A`, then `git commit -am "added name file"`, and `git push`.  This will push the new file to your copy of this repository!

Branches
--------
Now we'll go over a simple example of branching.  Branching is mostly useful for when you're working on a feature that you don't want integrated into the main codebase yet - sometimes new code can break functionality in a repository, so it's safer to put that code somewhere else until it's finished.

Go into your terminal and type `git checkout -b new_branch` (you can replace `new_branch` with whatever you want).  This creates a new *local* branch called `new_branch` and switches to it.  
