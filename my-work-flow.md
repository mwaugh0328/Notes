## Atom

**How do I work?** One part of my (new) workflow is the use of [Atom](https://atom.io/) which is a nice, functional, user friendly text editor.

**Why do I need a text editor?** I use a text editor for several purposes. First, I use it mostly for Markdown `.md` files. Markdown is simple text formatting language---that is you write the text and with simple commands markdown will format the document in a nice looking way. It gives you easier control over formatting than word, but a bit less control than `.tex` documents. Markdown also has the ability to be converted into HTML (the code behind websites). In fact, the [nyu data bootcamp](https://nyu.data-bootcamp.com/) website is written in Markdown. Atom also has a real time interpreter which allows you to see what your document looks like.

The second purpose for which I use a text editor is looking at data. Just like you would open up a `.csv` file in notepad (or Excel), a text editor can do the same. This is useful because a first step to data analysis is **always looking at the data.** Atom has a package that allows you to look at `.csv` files in a table formate, i.e. organized in way like excel.

Third, a text editor is always important for certain programing purposes. Given that I'm a big MATLAB user (sorry), I use it less for this purpose.

One final point---Atom is free and it appears to have a substantive community behind it. This means that the price is right and you won't be left helpless if you have a problem or there is a problem with Atom.

**Two useful Atom Packages**

- Table viewer. This is the [Tablr package](https://atom.io/packages/tablr) As mentioned above, this will open up `.csv` files and show it in a table format, much like excel. To install simply write this on the command line
```
apm install tablr
```
which is the command for installing the package tablr. To test, then open up a `.csv` file and see what happens. Note there are options to indicate that, e.g., your file has headers; you can also specify the delimiter; etc.

- Markdown tool bar. Since I'm new to markdown, having a tool bar (something that has the different options as buttons on a bar) is useful way to see and learn markdown. The tool bar package is [here](https://atom.io/packages/tool-bar-markdown-writer). To install, you have to install three packages in the following sequence
```
apm install tool-bar markdown-writer
apm install tool-bar-markdown-writer
```
Then when you open up a markdown file, the tool bar should be on the top.

- Markdown preview plus. This is an updated markdown previewer with the enhancement that it allows one to write math in LaTex. Very nice. All you do is use dollar signs (one, then math, the another for inline; two, then math, then two more for separate line. I think you need to disable the other markdown previewer before using (you do that by going file, settings, then finding the markdown previewer package and disabling). How to you install:
```
apm install markdown-previewer-plus
```
