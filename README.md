makefiles
=========

Makefile templates for WILDS projects.

- R
- Python


## What are these for?

A file called [Makefile][] (with no extension!) is a file used to run `make` commands. [make][] is a build automation tool. It's widely used, and can be used in projects regardless of the programming language(s) used in that project. 

There's [many language specific tools][buildtools] that are similar. For example, Ruby has [Rake][] and the `Rakefile`, and R has [targets][]. However, using and getting familiar with make is worth it as it's useful regardless of the project you're working on.

If a `Makefile` is in the root of a project, you should be able to type `make` and then a command, for example `make install` to install the package. Many terminal applications have plugins/extensions to tab autocomplete the make commands in the `Makefile`, which is a nice quality of life enhancement.

## How do I use these?

If you're working in an IDE like RStudio you may not find these Makefile's useful as the IDE has buttons that do a lot of what the Makefile does. 

To use one of these files, navigate to the file for either an R or Python package, and click the icon that says on hover "Download raw file". Put that file in the root of your project. 

After downloading the Makefile, you can edit it however you like, add new commands, remove commands, etc.

## Feedback

Open an issue if you have any thoughts, comments, feedback.



[make]: https://en.wikipedia.org/wiki/Make_(software)
[Makefile]: https://en.wikipedia.org/wiki/Make_(software)#Makefiles
[rake]: https://en.wikipedia.org/wiki/Rake_(software)
[buildtools]: https://en.wikipedia.org/wiki/List_of_build_automation_software
[targets]: https://docs.ropensci.org/targets/
