makefiles
=========

[![Project Status: Prototype – Useable, some support, open to feedback, unstable API.](https://getwilds.github.io/badges/badges/prototype.svg)](https://getwilds.github.io/badges/#prototype)

Makefile templates for WILDS projects.

- R
- Python


## What are these for?

A file called [Makefile][] (with no extension!) is a file used to run `make` targets. [make][] is a build automation tool. It's widely used, and can be used in projects regardless of the programming language(s) used in that project. 

There's [many language specific tools][buildtools] that are similar to `make`. For example, Ruby has [Rake][] and the `Rakefile`, and R has [targets][]. However, using and getting familiar with `make` is worth it as it's useful regardless of the languages you're working on.

If a `Makefile` is in the root of a project, you should be able to type `make` and then a target, for example `make install` to install the package. Many terminal applications have plugins/extensions to tab autocomplete the make targets in the `Makefile`, which is a nice quality of life enhancement.

## How do I use these?

If you're working in an IDE like RStudio you may not find these Makefile's useful as the IDE has buttons and keyboard shortcuts that do a lot of what the Makefile does and more. Where a Makefile comes into play is when you are working in a terminal.

To use one of thes Makefile's, navigate to the file for either an R or Python package, and click the icon that says on hover "Download raw file". Put that file in the root of your project. 

After downloading the Makefile, you can edit it however you like, add new targets, remove targets, edit targets, etc.

Important: Check if the paths used in various make targets are appropriate for your project, especially for Python projects where there's a lot more flexibility in structure of a package relative to R.

## Feedback

These Makefile's are a work in progress! Open an issue if you have any thoughts, comments, feedback.



[make]: https://en.wikipedia.org/wiki/Make_(software)
[Makefile]: https://en.wikipedia.org/wiki/Make_(software)#Makefiles
[rake]: https://en.wikipedia.org/wiki/Rake_(software)
[buildtools]: https://en.wikipedia.org/wiki/List_of_build_automation_software
[targets]: https://docs.ropensci.org/targets/
