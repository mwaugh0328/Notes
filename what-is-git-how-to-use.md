**What is Git? How do I use it?**

I'm still not sure! But here is my attempt at explaining what I know...

Git is a version control system. The basic idea is that it is a system which will record the changes made to a file. For example, as you modify and develop code, this is a way to retain the older version of your code, track the changes, and more! I'm still not at the more part... One final point: Git is local to your computer. This is what will distinguish it from GitHub which is a code/file/data repository that can store the code and the changes made.

It is very simple to download.

* Go [here](https://git-scm.com/) and follow the instructions... I don't know much so I just followed the default options. 
* Open GitBash which is basically the command line/terminal part of git. And enter the following commands which will assign you a username and an email. This will be relevant when interfacing with GitHUB

```
git config --global user.name "username"
git config --global user.email "username@email.com"
```

Now, I'm jumping ahead here. But what I like to do is to create a separate file called GitHub on my computer. It is from here that anything git related will be performed on. Note this is violating the spirit of the use of git, but bear with me.

Then in GitBash I change the directory so that it is operating within, I do this so...

```
cd c:/GitHub
```

Then I'm going to close a folder to my desktop from my github account. This will be my local version of the code from which I can make changes and so forth. In this case I do the following:

```
git clone https://github.com/mwaugh0328/JIE-SW-2014
```

which will then create a folder called "JIE-SW-2014" and will contain all the files that are posted on GitHub. Now do the following, type in

```
cd c:/GitHub/JIW-SW-2014
git status
```

where the first line changes the directory, the second line asks what is going on with the fils. In should reply back, \`\`on branch master'' and ''your branch is up to date with origin/master" In other words, your files are consistent as "master" file. Now do one more thing

```
git log --pretty=oneline
```

which then is going to show the different records associated with this file.

Let me do a couple of more things. I'm going to modify one of the files. Then it is worth seeing what is going on by asking about the status. It will show a message that will say to the effect...as far as git is concerned the relavent file they have is the master, but there is changed file that has not been committed. 

Ok so how do we commit. This is a key aspect of the git, we have made a change and are going to commit it to the record. To do so you go

```
git commit -am "a test"
git status
```

which \(i\) commits the modified file and then checking the status should show that current changes are consitent with the master, but the branch is one step ahead of the origin/master

Now I'm going to send the change back to GitHub the code repository. To do so I do

```
git push --all
```

which then pushes these files back to where they came from. Here a window should pop up asking for your username and login for GitHub. 

Here is something interesting to do, on another computer pull the folder and then check the status. What do you see? It should be something like, the origin master has the thing showing \`\`a test''



