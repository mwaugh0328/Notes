**What is Git? How do I use it?**

I'm still not sure! But here is my attempt at explaining what I know...

Git is a version control system. The basic idea is that it is a system which will record the changes made to a file. For example, as you modify and develop code, this is a way to retain the older version of your code, track the changes, and more! One final point: Git is local to your computer (or server). This is what will distinguish it from GitHub which is a code/file/data repository that can store the code and the changes made on the world wide web.

Here are some good (much better than mine) notes by the quant econ guys.

https://github.com/jstac/quantecon_nyu_2016/blob/master/lecture2/git_intro/gitnotes.md

---

**How to install**

This is relevant if you will work on local computer. Not if doing it on the server.

Step one-it is very simple to download....

* Go [here](https://git-scm.com/) and follow the instructions... I don't know much so I just followed the default options.
* Open the command prompt (or terminal). And enter the following commands which will assign you a username and an email. This will be relevant when interfacing with GitHUB

```
git config --global user.name "username"    
git config --global user.email "username@email.com"
```

---
**Basics of GIT**

Below, let me talk through about how to work with git, GitHub, and then files on your computer.

Below I will walk through this as if we are on the PIMS server.

Firs thing to do is to open up a terminal. This can be done by going to the ``launcher tab`` next to notbooks tab. From there is a button saying terminal. That will open up a command prompt/terminal like screen.

Just to get your orientation, here is one thing to do:

```
jupyter@73a36550b472:~$ dir
consumption_and_tradewar  quantecon-notebooks-datascience
```
so you type ``dir`` which will tell you about the folders currently in your "directory." In my case this is the quantecon stuff and then a repository that I had previously downloaded.


Then I'm going to clone a folder from GIHUB into the server. This will be my local version (i.e. it's stored on the server) of the code from which I can make changes and so forth. In this case I do the following:

```
jupyter@73a36550b472:~$ git clone https://github.com/mwaugh0328/ra_work_fall_2019.git

```
what this automatically does is it "clones" the repository (the folder structure, files, everything) onto your local computer (in this case the UBC server). When it does this you should see output that looks something like this:

```
Cloning into 'ra_work_fall_2019'...
remote: Enumerating objects: 4, done.
remote: Counting objects: 100% (4/4), done.
remote: Compressing objects: 100% (3/3), done.
remote: Total 4 (delta 0), reused 0 (delta 0), pack-reused 0
Unpacking objects: 100% (4/4), done.
```
And then if you ``dir`` you should see it there.

```
jupyter@73a36550b472:~$ dir
consumption_and_tradewar  quantecon-notebooks-datascience  ra_work_fall_2019
```
Also in the Jupyter Lab, in the file browser, you should be able to see the folder there and go in, etc.

Now from the terminal, you go into the folder. Do it like this

```
jupyter@73a36550b472:~$ cd ./ra_work_fall_2019
jupyter@73a36550b472:~/ra_work_fall_2019$ dir
README.md
```
The first line changes the directory, so now we are working in the ``ra_work_fall_2019`` folder. The second line says, what is there. And then it says that the readme.md file is there.

---
Useful command for working in a terminal (or command prompt)

- ``cd ../``  means go up in the directory
- ``cd ./`` means go down. So like above we went down.
- ``dir`` tells you about everything below where you address
- ``*`` is a wildcard that means takes the place of everything. It should be used carefully but is usefull when, for example, you want to save all python notebooks in the folder. So ``*.ipynb`` will do whatever to all files with ``.ipynb`` at the end. Another example would be ``mike*`` which would do whatever to all files that start with ``mike``. Powerfull, but might do more than you want.

---

Now here is an important command ``git status`` which asks that, within that directory, what is being tracked, how has it changed since the last actions taken. This may sound vague but bear with me. Here I will execute that command and we will see:

```
jupyter@73a36550b472:~/ra_work_fall_2019$ git status
On branch master
Your branch is up to date with 'origin/master'.

nothing to commit, working tree clean
```
In other words, your files are consistent as "master" file. And note this "master" file is consistent with the file on the hosted repository at GitHub.

Now lets change something. I'm going to create a new notebook and save it in the ``ra_work_fall_2019`` folder. **In your case, take one of the notebooks you have been working on and place it in the folder.** You can do this using the file browser in Jupyter Lab.

Now return to the terminal and type ``git status``
```
jupyter@73a36550b472:~/ra_work_fall_2019$ git status
On branch master
Your branch is up to date with 'origin/master'.

Untracked files:
  (use "git add <file>..." to include in what will be committed)

        mikes_test_nb.ipynb

nothing added to commit but untracked files present (use "git add" to track)
```
Ok so what this means is that (i) there is a file in the folder and (ii) it is not being tracked right now. So you can work on it, do what you will, but git is not tracking the changes.

Now here are two key aspects of git. Adding and committing changes. So first let's add the notebook.
```
jupyter@73a36550b472:~/ra_work_fall_2019$ git add mikes_test_nb.ipynb
jupyter@73a36550b472:~/ra_work_fall_2019$ git status
On branch master
Your branch is up to date with 'origin/master'.

Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)

        new file:   mikes_test_nb.ipynb
```
So what this did was add the file. Then I did status and it said there is a new file to be committed. Key thing now is that it is added, but it is still not being tracked. To track things we need to commit. The commit is a key aspect of git. Let's see how this works.

---
**Side issue**

when I did this I gotten
```
jupyter@73a36550b472:~/ra_work_fall_2019$ git commit -am "adding mikes notebook"

*** Please tell me who you are.

Run

  git config --global user.email "you@example.com"
  git config --global user.name "Your Name"

to set your account's default identity.
Omit --global to set the identity only in this repository.

fatal: unable to auto-detect email address (got 'jupyter@73a36550b472.(none)')
```
So here you enter in your email and username associated with your github account. I did this:
```
jupyter@73a36550b472:~/ra_work_fall_2019$ git config  user.email "waugh.e.michael@gmail.com"
jupyter@73a36550b472:~/ra_work_fall_2019$ git config  user.name "mwaugh0328"
```
**Note I removed the global part as it conflicts with the servers setup.**

---

Then do a commit and check the status
```
jupyter@73a36550b472:~/ra_work_fall_2019$ git commit -am "adding mikes notebook"
[master 7ff4a18] adding mikes notebook
 1 file changed, 61 insertions(+)
 create mode 100644 mikes_test_nb.ipynb
```
Ok so when I do the commit, I also do -am. This commits all and adds a message. Then my message is in quotes. Here a short, simple description is all that is needed. But it is important as it will highlight changes to the code.

What happened, it added the notebook and now it is being tracked. Then we can check the status of the repository like this...

 ```
jupyter@73a36550b472:~/ra_work_fall_2019$ git status
On branch master
Your branch is ahead of 'origin/master' by 1 commit.
  (use "git push" to publish your local commits)

nothing to commit, working tree clean
```
Notice what it says, the "branch" you are working on is ahead of the master (what you pulled from GitHub).

Now the next step is how to get the new file up to the code respository on GitHub. This is the second very important command which is the push.

Now I'm going to send the change back to GitHub the code repository. To do so I do

```
git push
```

which then pushes these files back to where they came from. Here a window may pop up asking for your username and login for GitHub. This is what happened for me:
```
jupyter@73a36550b472:~/ra_work_fall_2019$ git push
Username for 'https://github.com': mwaugh0328
Password for 'https://mwaugh0328@github.com':
Counting objects: 3, done.
Delta compression using up to 4 threads.
Compressing objects: 100% (3/3), done.
Writing objects: 100% (3/3), 689 bytes | 689.00 KiB/s, done.
Total 3 (delta 0), reused 0 (delta 0)
To https://github.com/mwaugh0328/ra_work_fall_2019.git
   e8595fa..7ff4a18  master -> master
jupyter@73a36550b472:~/ra_work_fall_2019$
```
Note that when you enter your password it will not display.

Then go in a browser to [https://github.com/mwaugh0328/ra_work_fall_2019](https://github.com/mwaugh0328/ra_work_fall_2019), what do you see?

**When do I make commits** This is a hard question, but essentially when you make tangible progress in the pieces of a project. Think of the commit as a placeholder where, maybe, I might want to go back to. It obviously makes no sense to commit after every little thing you do. But also only waiting till the very end of the day does not either since there were intermediate steps in the process you may want/need to revert to. But again, the commit is important, because it allows you to track what you have been doing while working on a project.

**Practice**

- Those notebooks you have worked on, can you add them to the repository?

---

### Advanced stuff---ignore for now


**How to Change Versions**

Ok, so this is one of the more important aspects of git. Let me walk through some commands to get a sense of what is possible.

First, checkout the log and below I'm printing the output

```    
$ git log --pretty=oneline
9c935cbfa518847cfdc950d5d21a125f6a87a74f (HEAD -> master, origin/master, origin/HEAD) Updated Git notes
982d88729ca4848819c51bf5b5f8f692bd6c8b49 Notes on how to use git
87cd42e4753e7bf55c83ba4733236f4084000fcd First Commit
01c0b612d80294360d80519b82e28430b3878bb2 Initial commit
```
Now the key thing to note are the number/letter combinations, these are recording the different committed versions. Not lets suppose that we want to return to a previous version. In that case you use the "checkout" command.
```
git checkout 902d88
```
And then this will revert your file to the version associated with "Notes on how to use git" commit. This is nice to see what you did in the past, etc. Then if you want to go back, you just do
```
git checkout master
```
And this will then return you to the latest commit.

Ok one more thing. Suppose you want to eliminate the previous commit and return the master to some earlier point. Note, this will permanently revert back, once you do it, all is lost(?)
```
git reset --hard 902d88
```
And then if you check the log, this will take you to
```
$ git log --pretty=oneline
982d88729ca4848819c51bf5b5f8f692bd6c8b49 (HEAD -> master, origin/master, origin/HEAD) Notes on how to use git
87cd42e4753e7bf55c83ba4733236f4084000fcd First Commit
01c0b612d80294360d80519b82e28430b3878bb2 Initial commit
```
which reverts everything back to the point where the master is not 982d88.

**How to Add Files**

---
Another important aspect of git. Ok so you save a new file or create a new folder within your repository. If you do `git status` you should see a message that says something to the following effect: on master, but there are untracked files within the repository. You want git to track those files, so what you need to do is to add them. The command is simple...

```
git add .
```
which says add files and then the `.` means add all untracked files in the repository. Then check the status again. It should say something to the effect that there you are on the master but that there are changes to be committed, and these changes shown should enumerate all the files you wanted to add. Now you just commit and you are done!

**How to Get Rid of Files**

First, this is dangerous territory, so be sure to know what you are doing before hand. So sometimes you want to reorganize your repository---this may include deleting files. What are the commands to do so. So something like

```
git rm your-file-to-delete
```
will do the trick.
