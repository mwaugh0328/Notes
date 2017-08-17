## How to use NAGs

**Tigger Warning:** I use MATLAB heaviliy. I can tell you are rolling your eyes right now, but I do...And this note is desighned to assit other users of MATLAB that are sometimes frustrated with its capibility at solving non-linear equations.

Let me paint a picture for you: You are solving a economic model computationally and must find a price vector that satisfies market clearing conditions. This is essentially a system of equations that you are looking for a solution to. The problem is that your solver is having a hard time doing this. If you use MATLAB you are probably using "fsolve" and you may be fighting withit a lot.

Here is a suggestion, use the solvers in [NAG](https://www.nag.com/). This is a company that provides propritory code/algorithims that can aid in the problem above. The "propritory" part is sometimes a problem since this means that access will cost money. Fortunatly, NYU has a license and can be accessed by simply contatcting the people at the [High Performance Computing Center](http://www.nyu.edu/life/information-technology/getting-started/software/high-performance-computing-software.html). Instalation instructions are straightforward.

---

## How to actually use NAGs
