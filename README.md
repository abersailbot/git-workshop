# AberSailbot - Git Workshop

This workshop will familiarise you with using git, and the reason for its use in version control.

You should first copy this repository so that you have your own version to work on for the time being.

On GitHub, you will see a "Fork" button on the top right hand side. You should fork this repository into your own account. This simply creates an exact copy on your own account that you have permission to work on.

Ensure that you are now in your own "Fork" of the repository (you should see YOURUSERNAME/git-workshop at the top of the page.


## Setup an SSH key (Only needed on Mac and Linux)

Git can either use SSH or HTTPS to communicate with a remote repository. The HTTPS method asks you for your password each time, but Github decided this was a security risk and stopped supporting it. The SSH method uses an SSH key and never asks for a password but requires more setup. 

If you're using Git for Windows every time you run a git clone, push or pull using HTTPS it will open a web browser and ask you to authenticate to github. This works fine, but is a bit annoying. 

On Mac and Linux (and Windows if you want to) you can create an SSH key instead. Do the following:

Open a terminal and type:

```ssh-keygen```

When asked which file to save the key as just press enter to use the default path. You'll then be asked (twice) for a passphrase used to protect the key, you can leave this blank if you don't want to enter a password each time you use the key.

The key will have two halves, a public half that you give to remote systems like Github and a private half that you keep safe. The private key should be stored in your home directory in the `.ssh` directory and it will probably be called `id_rsa.pub` or `id_ed25519.pub`. Open this file in a text editor or display at on your terminal by typing:

```cat ~/.ssh/id_rsa.pub```

Now copy and and paste the entire key, which will start "ssh-rsa" or "ssh-ed25519" and will end with your username@your computer name. In on Github click on the profile icon in the top right corner, choose Settings and then "SSH and GPG Keys" or go to https://github.com/settings/keys. Then click "New SSH Key" and paste in your SSH public key into the key box. ***DO NOT PASTE IN YOUR PRIVATE KEY***. Keys are usually specific to each computer you use, so enter the name of your computer in the title box.

### Test SSH connection

SSH to git@github.com

```ssh -T git@github.com```

You should get a response like:

```Hi username! You've successfully authenticated, but GitHub does not provide shell access.```

## Cloning a copy of your repository

To get a local copy of this repository (called "cloning" in git terms), run the following in a terminal to clone over SSH. Change YOURUSERNAME to your actual Github username. 

```git clone git@github.com:YOURUSERNAME/git-workshop.git```

Or if you using HTTPS:

```git clone https://github.com/YOURUSERNAME/git-workshop.git```

You should now have a new directory called git-workshop containing the files from this repository. Change into this directory with the cd command.

```cd git-workshop```

You can now try running the (somewhat useless) python code:

```python3 my_name.py```
    
    
## Making some changes to the code

Change the string in my\_name.py to something different (like your own real name) so that you get a different result when you run it.

You now want to let git know that you've changed something in the code. In order to do this, you need to tell git which file has changed with:

```git add my_name.py```

OPTIONALLY, if you'd like to see the changes git has now detected, you can run:

```git diff --cached```

Your changes have now been added to something similar to a staging area, ready to be
committed. In other words, you can now say that you want to make a note of the changes you have made and told git about.

This should be done with a `commit`:

```git commit```

A text editor should appear, in which you should add a message to your commit. Should you end up in the vi/vim text editor, see the bottom of this README for some handy shortcuts.

This message should describe briefly what the commit is, and why it was made.
This may be a description of a newly added feature, or a change to your existing code.
Your commit to this repository is simple and the purpose is known, so a short
message such as `Change name to my own` will suffice.


## Pushing your Commit to Github

When you're ready to "upload" this commit to the central repository (from your
local copy), you can run:

```git push```

If you want to get the latest changes made by someone else from a remote repository, run:

```git pull```
    
## Submitting a Pull Request

Your changes have been made to a fork (copy) of the original repository in the AberSailbot github. If you'd like to contribute your changes back to that repository you need to make a "pull request" asking the owner of the repository to pull from your fork. 

Github makes this easy, after you've pushed your changes Github should show a box at the top of the screen saying "This branch is 1 commit ahead of abersailbot:master." with a "Contribute" and "Fetch Upstream" button. 

Press the "Contribute" button, choose "Open Pull Request" and then click "Create Pull Request". You can then leave a comment describing what you've changed.

In this case it is probably only a small change with a single commit, but when doing this for real you might use this for much larger changes like adding whole new features or bug fixes. It is up to the owner of the upstream repository to reivew your pull request, decided if they want to accept it or if they want you to make further changes. 

# Vi/Vim Shortcuts

Whenever you want to run any commands in vi, press escape before doing so. This allows you to give commands. You can then use the following:

i - Press i in order to be able to start typing text at your current cursor position

:q - Quit without saving changes

:wq - Save your changes and quit

