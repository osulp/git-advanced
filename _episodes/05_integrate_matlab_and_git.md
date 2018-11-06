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

## Set up MATLAB with Git.

Right click
Source control
Manage Files
Select control integration: choose Git
Repository path: click Change
Add the path of your repository. Substitute the https part of the address for git. For example, if your repository path is https://github.com/username/matlab_example.git use instead git://github.com/username/matlab_example.git
Click validate. It should say Valid path in green. You may be asked for your login password for authentication. 
The sandbox should be your current folder. 
Click retrieve. 
All the files that you had in your repo should show up with a green circle next to them. 

## Add a file to the repo

Create a new file. For example, a file named git_practice.m
The file appears with a white circle next to it. It means that Git is not tracking this file yet. 
