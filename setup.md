---
layout: page
title: Setup
---

Please see [this section of the workshop page](https://osulp.github.io/workshop_intro_to_git/)
for instructions on installing Git.

We'll do our work in the `Desktop` folder so make sure you change your working directory to it with:

~~~
$ cd
$ cd Desktop
~~~
{: .language-bash}


If you have not been in the [Intro to Git - Beginner](https://osulp.github.io/git-beginner/) workshop make sure that you are comfortable with the concepts explained in the beginner workshop and that you create a repository (local and remote in GitHub) named planets so that we can work on it for the lesson. To create the repository planets you have two options:

## Option 1:
Take the following steps to prepare for this workshop:


Create a directory named planets in your Desktop
~~~
$ mkdir planets
$ cd planets
~~~
{: .language-bash}

Initialize a directory in the directory
~~~
$ git init
~~~
{: .language-bash}

Create a file named mars.txt with three lines of text. You can use any text editor you like, we will be using nano for the examples.
~~~
$ nano mars.txt
~~~
{: .language-bash}

Type the text below into the `mars.txt` file:

~~~
Cold and dry, but everything is my favorite color
The two moons may be a problem for Wolfman
But the Mummy will appreciate the lack of humidity
~~~

Add and commit the new file into Git

~~~
$ git add mars.txt
$ git commit -m "Start notes on Mars as a base."
~~~
{: .language-bash}

Create a GitHub account if you don't have one already. Start a new repository named planets. Enter a description if you like, and choose a Private repository. Do not initialize the repository with a README this time. Copy the url that GitHub provides (make sure that you are choosing the http option). It should look like `https://github.com/username/planets.git`.

~~~
$ git remote add origin https://github.com/vlad/planets.git
~~~
{: .language-bash}

Push the changes from our local repository to the repository on GitHub:

~~~
$ git push origin master
~~~
{: .language-bash}


That's all!

## Option 2
Alternatively, you can also clone this repository [https://github.com/clarallebot/planets](https://github.com/clarallebot/planets) that has more or less the same information. 

Click on the Fork button in the planets repository. It is on the top right. Once GitHub has finished forking clone the repository in your computer. Make sure that you are in the right folder. For example, if you want this to be in the Desktop:

~~~
$ cd
$ cd Desktop
~~~
{: .language-bash}

Then clone the repository in your computer

~~~
$ git clone https://github.com/username/planets.git
~~~
{: .language-bash}

You should be all set. 

# Review the content in the beginner lesson

If the instructions of option 1 or option 2 do not sound familiar, we suggest that you come to the Beginner workshop too. 

If you are planning on coming to the advanced workshop but are not attending the beginner workshop we suggest that you take a quick look at the [Version control with Git: Beginner](https://osulp.github.io/git-beginner/) lesson to make sure that you have all the concepts fresh. 

Let us know if you have any questions!

[workshop-setup]: https://carpentries.github.io/workshop-template/#git
