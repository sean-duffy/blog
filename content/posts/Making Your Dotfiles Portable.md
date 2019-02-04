---
title: "Making Your Dotfiles Portable"
date: 2013-09-16T10:00:00Z
draft: false
---

As a developer I use command line programs like Vim and Git on a daily basis, and like most developers I like to have them configured in a way particular to my liking. For this reason I've recently made a move which allows my configuration files, or dotfiles as they are known, to be portable across any computer or remote server I happen to be working on.

My method of doing this uses a hosted Git repository and a simple bash script. This setup also has the benefit that it puts my dotfiles under distributed source control, and allows me to share them with others by using a public repository on GitHub. This post is a brief tutorial on how to use this method yourself.

The first step is to move all the dotfiles you're interested in to an unhidden folder called *'dotfiles'* in your home directory. This allows you to edit and view them more easily and avoids the mess of initialising a Git repository in your home directory. For example if you were moving your Vim configuration, you'd do the following.

<script src="https://gist.github.com/sean-duffy/fe7d7579c996e3a29ef7.js"></script>

Next, you should initialise a git repository in your dotfiles directory, adding all of the dotfiles you've put in there and making your initial commit. You can then create a repository on GitHub or another Git hosting service and add it as a remote for the repository you created in the dotfiles directory. To do that, I did this.

<script src="https://gist.github.com/sean-duffy/2471d34fffe35a18cf16.js"></script>

Now your dotfiles are portable, and to get them onto the machine you're using all you have to do is **git clone** your hosted repository. However the configuration won't work yet, as they're in your dotfiles directory and the relevant programs can't find them there. This problem is solved by a simple bash script which creates symlinks from the home directory to each of the files in your dotfiles directory.

<script src="https://gist.github.com/sean-duffy/ab88875fd7ccd90372ec.js"></script>

This script will create symlinks from the home directory for all of the unhidden files in your dotfiles directory except for *'README.md'*, since if your repository is public you'll probably want one of these, but you won't want a symlink created for it. To use this script just save it in your dotfiles directory as *'.make'*. To run it, you'll have to make it executable using the following command.

<script src="https://gist.github.com/sean-duffy/dfec7401beb66a9f55c0.js"></script>

Now your dotfiles are portable and can be accessed by their respective utilities, and each time you're on a different machine where you'd like your settings, all you have to do is delete any occurrences of the dotfiles you want to use, clone in your own dotfiles from GitHub and run the make script. In my case, I do the following.

<script src="https://gist.github.com/sean-duffy/cdf8a3270f0ff76e93a1.js"></script>

I hope you enjoyed this post, if you found it helpful or need some help, please feel free leave a reply in the comments!
