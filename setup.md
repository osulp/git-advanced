---
layout: page
title: Setup
---

Please see [this section of the workshop page][https://osulp.github.io/workshop_intro_to_git/]
for instructions on installing Git.

We'll do our work in the `Desktop` folder so make sure you change your working directory to it with:

~~~
$ cd
$ cd Desktop
~~~
{: .language-bash}


If you have not been in the [Intro to Git - Beginner](https://osulp.github.io/git-beginner/) workshop make sure that you are comfortable with the concepts explained in the beginner workshop and take the following steps to prepare for this workshop:


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


[workshop-setup]: https://carpentries.github.io/workshop-template/#git
