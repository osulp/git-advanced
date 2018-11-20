---
title: Branches
teaching: 25
exercises: 0
questions:
- "How do I create a branch for my project?"
objectives:
- "Understand what branches are and what they are good for"
- "Create a new branch"
- "Switch between branches"
- "Merge branches"
keypoints:
- "`git branch` creates a branch."
- "`git checkout` allows you to switch between branches"
- "`git merge` to merge branches"
---

Often you may want to test out a new feature in some code. You may or may not decide you want to keep this feature and in the mean time you want to make sure you have a version of your script you know works. [Branches](reference#branch) are instances of a repository that can be edited and version controlled in parallel. You can think of it like making an entire copy of your repository folder that you can edit, without affecting the original versions of your scripts. The advantage of using git to do this (rather that making a repo_copy folder on your computer), is that you can use git tools to manage this code while it's under development and you have the ability to seamlessly merge in your changes to your originals.  

To see what branches are available in your repository, you can type `git branch`. First let's make sure we are all in the planets directory in our home folder:

~~~ 
$ cd ~/planets
$ git branch
~~~
{: .language-bash}

~~~ 
* master
~~~
{: .output}

The master branch is created with the repository is initialized. With an argument, the `branch` command creates a new branch with the given name. Let's make a new experimental branch:

~~~ 
$ git branch experimental
~~~
{: .language-bash}

~~~
  experimental
* master
~~~
{: .output}

The star indicates we are currently in the master branch of our repository. To switch branches, we use the `git checkout` command to checkout a different branch. 

~~~
$ git checkout experimental
$ git branch
~~~
{: .language-bash}

~~~
Switched to branch 'experimental'

* experimental
  master
~~~
{: .output}

We have some updated information on pluto, but we aren't sure that we will want to include in our final report. Let's make some updates to the `pluto.txt` file in this experimental branch:

~~~
$ nano pluto.txt
$ cat pluto.txt
~~~
{: .language-bash}

~~~
It is so a planet!
A planet with a charming heart on its surface; What's not to love?
~~~
{: .output}

We've made this change on our experimental branch. Let's add and commit this change:

~~~ 
$ git add pluto.txt
$ git commit -m "Breaking updates about Pluto"
~~~
{: .language-bash}

~~~
[experimental c5d6cba] Breaking updates about Pluto
 1 file changed, 1 insertion(+)
~~~
{: .output}

We've committed these changes locally, but we need to push these changes and our new branch to GitHub. To do so, we enter the following command:  

~~~
$ git push origin experimental
~~~
{: .language-bash}

~~~
Counting objects: 5, done.
Delta compression using up to 4 threads.
Compressing objects: 100% (3/3), done.
Writing objects: 100% (3/3), 307 bytes, done.
Total 3 (delta 2), reused 0 (delta 0)
To https://github.com/vlad/planets.git
 * [new branch]      experimental -> experimental
~~~
{: .output}

Note that in the past we've types `git push origin master` when pushing to our remote.
This was because we were making changes on our `master` branch and pushing to the remote named `origin`.
Here, we've been working on our `experimental` branch. To push those changes to GitHub, we therefore specify that we want to push the `experimental` branch to the remote named `origin`. 

Let's check our status:

~~~
$ git status
~~~
{: .language-bash}

~~~
On branch experimental
nothing to commit, working directory clean
~~~
{: .output}

You can see from the git status output that we are on the experimental branch rather than the master branch. Let's examine the master branch to ensure the original version of our `pluto.txt` doesn't include this sentimental statement:

~~~
$ git checkout master
~~~
{: .language-bash}

~~~
Switched to branch 'master'
~~~
{: .output}

~~~ 
$ cat pluto.txt
~~~
{: .language-bash}

~~~
It is so a planet!
~~~
{: .output}

As you can see, the master branch does not include our updated notes about Pluto. 
If we look on GitHub, we can switch between the `master` and `experimental` branch and see the same difference between the two versions of `pluto.txt`. 
We are pretty confident that the heart in Pluto is charming, so let's fold in all of the changes that we've made on the experimental branch into our master branch. 
To merge two branches together, ensure you are located in the branch you want to fold changes into. 
In our case, we want to be in the master branch:

~~~ 
$ git branch
~~~
{: .language-bash}

~~~
  experimental
* master
~~~
{: .output}

Excellent, we are in the right place. To fold the experimental branch into the master branch, we use the `merge` function of git followed by the name of the branch we want to fold in:

~~~
$ git merge experimental
~~~
{: .language-bash}

~~~ 
Updating ee530d7..c5d6cba
Fast-forward
 pluto.txt | 1 +
 1 file changed, 1 insertion(+)
~~~
{: .output}

Now if we look at our `pluto.txt` file, we see our updates from the experimental branch:

~~~
$ cat pluto.txt
~~~
{: .language-bash}

~~~
It is so a planet!
A planet with a charming heart on its surface; What's not to love?
~~~
{: .output}

Now let's push these changes up to github:

~~~
$ git push origin master
~~~
{: .language-bash}

~~~
Total 0 (delta 0), reused 0 (delta 0)
To https://github.com/vlad/planets.git
   a822910..10ed071  master -> master
~~~
{: .output}

> ## Pushing all branches to GitHub
> If you've been working on multiple branches and want to push commits from all branches to GitHub, you can use the following syntax rather than pushing each branch individually:  
>
> `git push --all origin`
{: .callout}


We no longer have a use for our experimental branch. To delete a branch you don't need, you can use the `-d` flag of `git branch`:

~~~ 
$ git branch -d experimental
~~~
{: .language-bash}

~~~
Deleted branch experimental (was c5d6cba).
~~~
{: .output}

> ## Deleting a remote branch 
> You've deleted your experimental branch locally, but if you look on your GitHub page, you'll see it still exists, even if you `git push --all origin`. 
> To delete the branch remotely, you should use the syntax:    
>
> `git push origin <local-branch>:<remote-branch>`  
>
> In our example this is: `git push origin experimental:experimental`.
> You can also use the shorthand version: `git push origin :experimental`. 
> Using this notation, Git assumes you are listing the remote branch and want to push the branch you are currently in on the local repo. 
> Essentially you are pushing "nothing" to the remote branch, which erases it.
{: .callout}


> ## Creating and Merging Branches 
>
> In your `bio` repository you made earlier, do the following:  
> 1. Create a branch called `grad_school`  
> 2. Create a file called `thesis` and write one line about your research (or something about science if you don't know what you'll be researching yet)  
> 3. Merge those changes back to the master branch of `bio`.
{: .challenge}
