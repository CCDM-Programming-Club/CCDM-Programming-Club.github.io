---
title: "Tips for absolute beginners."
layout: "post"
---

Today we identified some important barriers to our group progressing forward.
It seems like we need to take a step back and get our beginners up to speed,
and to set some clearer expectations of what you should do between sessions.

I see programming club as something that you should be able to tackle after going to an
event like [software carpentry](http://swcarpentry.github.io).
I think we'd like it to continue pitching it at a slightly higher level than absolute basics,
but I don't think that means beginners shouldn't come.
It does mean that you'll have some homework to do between sessions,
and we'll try to point you towards good resources so that you can catch up quickly.
Again, lots of these topics would be covered in a software carpentry workshop, so enroll in one of those if you haven't already.


I would say that the following things are required for you to be able to work.

1. A bash/zsh command line environment.
2. A good text editor.
3. Python (or any programming language, but it seems like most beginners are gravitating towards python).
4. Git.


## 1. Setting up your computer.

Software carpentry instructions are here <http://swcarpentry.github.io/shell-novice/setup.html>.
There are some good links at the bottom of that page for windows users.

Please just use MacOS, a Linux distribution (e.g. [Ubuntu](https://www.ubuntu.com/)), or Windows 10 with [windows subsystem for linux (wsl)](https://docs.microsoft.com/en-us/windows/wsl/install-win10) enabled.
If you are using an older version of Windows, ignore the instructions for Git bash, Cygwin or Putty, and just install a linux virtual environment inside of [VirtualBox](https://www.virtualbox.org/wiki/Downloads).
Unfortunately, Windows neglected the command line needs of developers and scientists for a long time, so now most of the expertise and tooling is centered around Unix-like systems (hence WSL).

You can also dual boot your computer to have both Linux and Windows.
You can talk to James about the relative benefits of Dual boot vs Virtual machines if you like.
I've followed [these](https://www.howtogeek.com/214571/how-to-dual-boot-linux-on-your-pc/) instructions before, and I don't think the process has changed much.


## 2. Find a text editor that you like.

There are specialised text editors that you can use for writing code that highlight syntax for you or give you suggestions as you write.
Here are some good options:

- [Visual studio code](https://code.visualstudio.com/). The best thing Windows has ever made for coding.
- [Atom](https://atom.io/)
- [Sublime text](https://www.sublimetext.com/)
- [Notepad++](https://notepad-plus-plus.org)
- [Vim](https://www.vim.org/). Darcys favourite. Not easy to use though.
- [Emacs](https://www.gnu.org/software/emacs/). Robs favourite. Not easy to use either.


## 3. Get to know your command line.

Assuming everything is working you can now get started with the command line (e.g. Bash).

Work through some of the exercises in the software carpentry workshops:

- <http://swcarpentry.github.io/shell-novice/>
- <http://swcarpentry.github.io/shell-extras/>


Also you should make sure you have some sort of package manager installed.
Installing software libraries manually is painful, package managers are your friends :).
If you're using Linux or WSL you can use the Linux distributions package manager
(e.g. For Ubuntu that might be `apt`, [Tutorial here](https://itsfoss.com/apt-get-linux-guide/)).

To my knowledge Macs still don't have a built in package manager.
Most people seem to use [Homebrew](https://brew.sh/).

## 4. Installing python3.

This seems to be the biggest barrier to people right now.
Software carpentry has a good introduction to installing on different operating systems using [Anaconda](https://www.anaconda.com/what-is-anaconda/).
Check out the videos for a step-by-step instruction.
Note that for those using WSL you might like to follow the linux command line instructions from your Linux bash session.

- <http://swcarpentry.github.io/workshop-template/#python>

Anaconda is a good way to get you started quickly with a bunch of extras included.
I personally feel that it's a bit bloated, but you can learn how to manage things better as you gain experience.


## 5. Install some python packages.

You might want to install some packages to get running.
Packages like, [numpy](http://www.numpy.org/), [pandas](http://pandas.pydata.org/), and [jupyter](http://jupyter.org/) are extremely commonly used packages in python.
Perhaps more relevant to bioinformatics is [biopython](https://biopython.org/).

### Pip and virtualenv

Base python has a few options for installing packages and keeping them organised.
This tutorial seems to be a good introduction to some of those options: http://docs.python-guide.org/en/latest/dev/virtualenvs/
It doesn't really matter which one you use, they all essentially do the same thing.

Pipenv seems like a good option to try out <https://docs.pipenv.org/>


### Conda and conda env

If you installed Anaconda python, you probably have most packages that you want installed.
If not the anaconda website has a lot of good information about installing packages.

- Using conda environments <https://conda.io/docs/user-guide/tasks/manage-environments.html>
- Installing python packages in conda <https://conda.io/docs/user-guide/tasks/manage-pkgs.html>


From my perspective, conda and virtualenv serve two communities that we are at the intersection of.
Conda tends to focus more on "data science" types who want to get started quickly,
while virtualenv tends to be for the more software development crowd because you get more control over it.

Again, just use whichever one makes the most sense to you.


### Using Jupyter

Assuming that you have the previous steps done, installing and running jupyter should be easy
<http://jupyter.org/install>.
Head over to the notebook documentation for instructions on how to use <https://jupyter-notebook.readthedocs.io/en/stable/>.
Or here's a video <https://www.youtube.com/watch?v=HW29067qVWk> (The actual tutorial starts at about 3 minutes).

Jupyter is a convenient tool for working with python interactively.
But there are a lot of cases where they aren't appropriate, e.g. very long running scripts or projects where you will be processing different data using the same processes.
In those cases you should really be writing scripts, which is more the focus of programming club.
I tend to use Jupyter notebooks when I need to plot things or process a single data set, or if I just need to prototype something quickly.



## 6. Learning Python.

Again, the software carpentry workshops are a good place to get started, but they rely a lot on external tools like numpy and matplotlib (
<https://swcarpentry.github.io/python-novice-inflammation/>).

I would suggest in addition to the software carpentry workshop you have a look at these and see what gels for you:

- <http://rosalind.info/problems/list-view/?location=python-village>
- <https://www.datacamp.com/courses/intro-to-python-for-data-science/>
- <https://python.swaroopch.com/first_steps.html>

But once you've been through some basic tutorials, there's no point trying to remember everything or learn it all at once.
Get started solving some actual problems (like the rosalind ones) and google things that you need to know as you go.
E.g. "how do I read a file in python" or "how do I split a string in python".

The official python tutorial is also a good place to look.
It's quite a technical tutorial, but that makes it a good reference to look through when you need to know something specific (https://docs.python.org/3/tutorial/index.html).

You can also read through the previous post [Tips for python beginners](https://ccdm-programming-club.github.io/2018/05/25/tips-for-python-beginners.html) to get some extra information.


## 7. Install and get the hang of git.

[Git](https://git-scm.com/) is a version control system that makes keeping track of your code, and working with other people really easy (well easier).
Github has a great interactive tutorial to introduce you to git <https://try.github.io/levels/1/challenges/1>.
Software carpentry also has a lesson on Git <http://swcarpentry.github.io/git-novice/>.

[Github](https://github.com/) is one website that will host you git repositories for you, and it has a fun mascot!
If you create a Github account, send Rob or I your username so that we can add you to our official [Github organisation](https://github.com/orgs/CCDM-Programming-Club).



I hope this helps those of you who were a bit confused today, and that you continue to come along :)
I think the task for you in the next two weeks is to get your software set up, and to get comfortable with coding.
If you can attempt the first two Rosalind exercises, that would be great but if you can't quite get there that's ok too.

Cheers, Darcy
