** Atom**

*How do I work?* One new part of my workflow is the use of [Atom](https://atom.io/) which is a very nice, very functional, user friendly text editor.

*Why do I need a text editor?* I use one for several purposes. First, I use it mostly for Markdown `.md` files. Markdown is simple text formatting language---that is you write the text and with simple commands it will format it in a nice looking way. Markdown also has the ability to be converted into HTML (the code behind websites). In fact, the nyu data bootcamp website is written in Markdown. Atom happens to have a real time interpreter which allows you to see what your document looks like.

The second purpose that I use a text editor is for data. Just like you would open up a `.csv` file in notepad (or excel), a text editor can do the same. This is useful because a first step to data analysis is always looking at the data. Atom has a very nice package that allows you to look at `.csv` files in a organized way like excel.

Third, a text editor is always important for certain programing purposes. Given that I'm a big MATLAB user (sorry), I use it less for this purpose.

One final point---Atom is free and appears to have a substantive community behind it. This means that the price is right and you won't be left helpless if you have a problem or there is a problem with Atom.

** Two useful Atom Packages **

- Table viewer. This is the [Tablr package](https://atom.io/packages/tablr) As mentioned above, this will open up `.csv` files and show it in a table format, much like excel. To install simply write this on the command line
```
apm install tablr
```
which is the command for installing the package tablr. To test, then open up a `.csv` file and see what happens.

- Markdown tool bar. Since I'm new to markdown, having a tool bar (something that has the different options as buttons on a bar) is useful way to see and learn markdown. The tool bar package is [here](https://atom.io/packages/tool-bar-markdown-writer). To install, you have to install three packages in the following sequence
```
apm install tool-bar markdown-writer
apm install tool-bar-markdown-writer
```
Then when you open up a markdown file, the tool bar should be on the top.
