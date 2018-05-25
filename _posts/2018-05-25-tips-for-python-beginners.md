---
layout: post
title: "Tips for python beginners."
---

In Programming club we are taking a "learn by doing and sharing" approach.
However we acknowledge that for a new-comer, learning where to find information
can be intimidating.
With that in mind, here's a list of useful packages/links to get you started
with python in the sort of space that we're working in.


Note that we aren't necessarily tied to the Python language in this group, but 
it's a reasonable suggestion for beginners that shouldn't be too offensive to
anyone.


## General python

- Use python 3!!!
- <https://docs.python.org/3/tutorial/index.html> should often be your first
  place to look through if you don't know what to search for.
- Google, e.g. how do i do 'x' in python? Someone has almost always asked
  something similar on [stack overflow](https://stackoverflow.com/) or [biostars](https://www.biostars.org/) etc.
- Python came with a philosophy about how to make code readable and understandable
  <http://docs.python-guide.org/en/latest/writing/style/>. Sometimes you'll see 
  people talk about the 'pythonic' way to do something. This is usually what they mean.


## Generally useful modules

- [collections](https://docs.python.org/2/library/collections.html) contains
  additional datatypes to the basic list, tuple, dicts. Useful ones include a
  counter and defaultdict.
- [collections.abc](https://docs.python.org/3.7/library/collections.abc.html#module-collections.abc)
  have a collection of abstract base classes.
  If you miss Java's interfaces or Haskell's typeclasses, this might be for you.
- [subprocess](https://docs.python.org/3/library/subprocess.html) offers ways of
  calling shell programs and/or operating system Pipes.
- [sys](https://docs.python.org/3/library/sys.html) see section in command line arguments.
- [os](https://docs.python.org/3/library/os.html) gives functions for getting
  information about files, moving or copying files, manipulating file paths 
  in an OS agnostic manner etc.
- [itertools](https://docs.python.org/3/library/math.html) provides utilities for
  looping nicely in python.
- [functools](https://docs.python.org/3/library/functools.html) provides a few
  ways of working in a more 'functional' way, e.g. using `reduce` and `partial`
  (curried) functions.
- [csv](https://docs.python.org/3/library/csv.html) helps you parse delimited files without having to worry about handling quoting etc.
  You could also use pandas for this, but csv is in the standard library. 
  Similar packages exist for [json](https://docs.python.org/3/library/json.html),
  [yaml](https://github.com/yaml/pyyaml) (NB not in std lib),
  and [xml](https://docs.python.org/3/library/xml.etree.elementtree.html) parsing.

## Installing packages and virtual environments

Use a virtual environment (or conda) when you can.
Most linux distributions now use python in some core applications, so changing
python package versions can mess with your OS.
Never use `sudo pip install ...` for this reason, use an environment or the 
OS's official package manager.

- [pip](https://pip.pypa.io/en/stable/quickstart/) is the official way of
  installing packages (can usually be installed using `apt` or `dnf` or `brew`).
- [conda](https://conda.io/docs/) A more general package manager that's allows 
  installing of most software. Also supports it's own environment isolation system.
- [virtualenv](https://virtualenv.pypa.io/en/stable/) is a way of installing
  python packages separately for different "environments". This is useful if 
  programs run different versions of python packages etc.


## Unit testing

- [unittest](https://docs.python.org/3/library/unittest.html) pythons official
  unittesting framework. It is comprehensive but complicated.
- [pytest](https://docs.pytest.org/en/latest/) A simpler testing framework.
  Tests are run using simple `assert` statements.
  More complex testing can be performed using `fixtures` and decorator functions
  rather than classes.
- [mock](https://docs.python.org/3/library/unittest.mock.html) contains
  utility functions to use unittests more effectively, and remove dependencies
  between functions/methods/classes.


## Parsing command line arguments

- [argparse](https://docs.python.org/3/library/argparse.html) is pythons current
  official cli solution. It provides a similar interface to the
  [getopt](https://www.gnu.org/software/libc/manual/html_node/Getopt.html) interfaces,
  but is much easier to use and extend.
- [sys](https://docs.python.org/3/library/sys.html) gives you access to
  command line arguments via `sys.argv`. It also contains some extra info about
  the operating system/environment (also see [os](https://docs.python.org/3/library/os.html)).
  It allows you to access stdin, or write to stdout/stderr via `sys.stdin`, `sys.stdout`, or `sys.stderr`.


## Biological data

Common bioinformatics file parsers and data structures are generally available
in packages already, so there isn't usually a need to write your own.
However, for learning exercises in rosalind I would encourage you to avoid
using these packages because you'll miss out on some useful skills.

- [biopython](http://biopython.org/) has lots of functions for doing bioinformatics/general computational biology.
- [scikit-bio](http://scikit-bio.org/) some people didn't like biopython, so decided to reinvent the wheel and never quite finish it.
  It backs most of QIIMEs functionality so it's often useful though.
- [gffutils](https://pythonhosted.org/gffutils/) is one of the better gff parsers/manipulators in python.
  It is generally very fast, but also very strictly adheres to the GFF3 spec, so you'll often find yourself having to hack it a bit.
- [pybedtools](https://daler.github.io/pybedtools/) a wrapper around bedtools that is often a bit nicer that doing it on the command line.
- [pysam](https://github.com/pysam-developers/pysam) is a wrapper around the C/C++ libraries powering samtools/bcftools.
  Very useful for working with BAM and VCF files directly, or just for general speedy-ish bioinformatics.


## Numerical python

- [math](https://docs.python.org/3/library/math.html) basic mathematical operations, e.g. `abs`, `ceil`, `factorial`.
- [numpy](http://www.numpy.org/) allows you to do efficient numerical operations
  from within python. It is similar to matlab or Julia's array system, or R's vectors and matrices.
- [scipy](https://www.scipy.org/) offers lot's of functions/datatypes for numerical data.
  Lot's of statistics, modelling, linear algebra etc is implemented here, and build on top of numpys array system.
- [pandas](http://pandas.pydata.org/) offers dataframes in python.
  They're a little bit more verbose than in R or SQL, but it's very nice nonetheless.
  Also built on top of numpy.
- [matplotlib](https://matplotlib.org/) pythons best but most frustrating plotting library.
- [seaborn](https://seaborn.pydata.org/) is matplotlib for humans/ggplot2 users.
- [bokeh](https://bokeh.pydata.org/en/latest/) offers interactive plots.


## Jupyter

Jupyter notebooks are a convenient way to keep code and your comments alongside
your results, much like a Rmarkdown-knitr document or Emacs Org-mode doc.

I suggest installing `jupyter` in a virtual (or conda) environment, and giving it a go.
There are a lot of youtube videos that can introduce you to how it works.

I would caution new users against doing everything in jupyter notebooks.
Jupyter is convenient, but it seems to mess with pythons Garbage collection so you
may find yourself running out of memory if you do high-memory work in it.
If you need performance, write a script!

- [jupyter notebook](https://jupyter-notebook.readthedocs.io/en/stable/) basics.
- [jupyter lab](http://jupyterlab.readthedocs.io/en/latest/) is the new interface,
  which is quite similar to Rstudio. I don't like it as much as the regular notebooks.

