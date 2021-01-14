---
title: Integrate Matlab and Git
teaching: 15
exercises: 0
questions:
- "How can I version control my MATLAB files with Git?"
objectives:
- "Set up MATLAB to facilitate version control with Git"
keypoints:
- "MATLAB has built in features that will help you keep version control of your MATLAB scripts."
---

Most programming languages can be integrated with Git. If you code using a text editor, know that there are some that offer a good integration with Git, such as [Atom](https://atom.io/). If you use a programming language that involves an interface to work with it, like Matlab, it is worth taking some time to learn how to work with it.  


## Set up MATLAB with Git.

The first step is to create a repository with Git. There is a reminder for how to do this [here](https://osulp.github.io/git-beginner/07-github/index.html). For this exercise we will create a new repository named "matlab_example", but make sure that you choose better names than this for your real repositories. In this case this newly created repository is in [https://github.com/clarallebot/matlab_example](https://github.com/clarallebot/matlab_example). 

Now we go to our folder where we have the files that we want to version control, and right click. Select Source Control and then Manage Files. 

![Select Source Control and Manage Files](../fig/git_with_matlab_cloning_repo-01.png)

A new screen named "Manage Files Using Source Control" will appear. Choose Git as the Source control integration. 

![Choose Git as Source control integration](../fig/git_with_matlab_cloning_repo-02.png)

Click on Change and add the path of your repository. Go to the repository in Github and click on "Clone or Download". Copy the link. The link will look like `https://github.com/username/matlab_example.git`. Change the https at the beginning with a `git` so that it looks like `git://github.com/username/matlab_example.git`. You may be asked for your login password for authentication. Unfortunately just copying pasting the html path to your repository or copying the link provided by github under "Clone or Download" will not work. 

![Change the repository path](../fig/git_with_matlab_cloning_repo-03.png)

Click validate. If you have introduced the wrong path you will get something like 

![Change the repository path Error](../fig/git_with_matlab_cloning_repo-04.png)

Hopefully everything worked correctly and you get a green Valid path message after validating:

![Change the repository path Success](../fig/git_with_matlab_cloning_repo-05.png)

When you are back to the Manage Files Using Source Control panel make sure that the sandbox is the path to your current folder, the one that you want to version control with git. Click retrieve. All the files that you had in your repo should show up with a green circle next to them. If you created the repo with a readme file you should see the readme file in your folder. 

![Files added to the repo](../fig/git_with_matlab_cloning_repo-06.png)

## Add a file to the repo

Create a new file. For example, a file named git_practice.m We can write anything in it, like a comment line. 
The file appears with a white circle next to it. It means that Git is not tracking this file yet. 

![New file has a white circle next to it](../fig/git_with_matlab_adding_files-01.png)

To add the file right click on the file and select Add to Git. 

![New file has a white circle next to it](../fig/git_with_matlab_adding_files-02.png)

After adding the file, the symbol next to the file will be a plus sign. 

![New file has a plus sign next to it](../fig/git_with_matlab_adding_files-03.png)


## Commit

Now we want to commit the file that we just added. To do that we right click on the empty space of our folder and choose `Source Control` and then `View and Commit changes`. 

![Open commit window](../fig/git_with_matlab_commit-01.png)

The new window offers us the opportunity to add a comment: Add new git_practice file to the repository. 

![Add comment to commit](../fig/git_with_matlab_commit-02.png)

After clicking Commit the git_practice.m file has a green circle next to it. This means that it has been commited locally. 

![Committed file](../fig/git_with_matlab_commit-03.png)

The source control menu has a push option. Selecting this option will push the changes that we saved in our local repository to our remote GitHub repository. 

Choose `Push` from the Source control menu to push to the remote repository.


NOTE: this lesson has been developed using the information in [Mathworks and Git](https://blogs.mathworks.com/community/2014/10/20/matlab-and-git/), a post by Ned Gulley on MathWorks Blogs. 
