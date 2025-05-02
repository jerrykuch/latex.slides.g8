# latex.slides.g8

__TODO:__ Update this README file to reflect what I actually did here...

Unofficial opinionated [Giter8][g8] template for latex beamer slides, using metropolis style

**HIGHLY WIP**: don't trust the selection of plugins or the part of the code that have not been properly templatised/parametrised yet.


## Create a new project

Assuming `sbt` is installed on the machine, 
```bash 
sbt new alessandrocandolini/latex.slides.g8 --name=<name> --title=<title> --author=<project author> --force
```
or from a local clone of the repo (be careful to pull the latest changes locally before running the command)
```bash 
sbt new file:///<local-checkout-dir>/latex.slides.g8 --name=<name> --title=<title> --author=<project author> --force
```
`name` will be used as folder name (a new folder will be created if not present), title for slides title (can be edit later). By default, the author is set to be my personal name if not explicitly provided. 

Alternatively, assuming `g8` is installed on the machine (see next section), it is also possible to generate a new project from a local clone of the repo by using `g8` like follows: 
```
g8 file:///<local-checkout-dir>/latex.slides.g8/ --name=<name> --title=<title> --author=<project author> --force
```

See http://www.foundweekends.org/giter8/usage.html#Usage for more details

### Install Giter8

On MAC OS X, both `sbt` and `giter8` are available via the Homebrew package manager:
```
brew update
brew install sbt
brew install giter8
```

For more options, refer to the original documentation in https://www.scala-sbt.org/ and http://www.foundweekends.org/giter8/setup.html respectively. 

## Giter8 crash course


* Giter8 generates a project that has exactly the same structure of the [src/main/g8](src/main/g8) folder
* template variables are defined in the [default.properties](src/main/g8/default.properties) file
* template variables can be accessed as `$name of the variable$` (ie, between `$`) from everywhere
* `$` is the reserved symbol, whenever you need to use a `$` for purposes other than referring to a template variable be sure to escape it as `\$`; this is a typical source of errors

A more comprehensive guide here: http://www.foundweekends.org/giter8/Contents+in+Depth.html

Template license
----------------
Written in 2022 by Alessandro Candolini alessandro.candolini@gmail.com

To the extent possible under law, the author(s) have dedicated all copyright and related
and neighboring rights to this template to the public domain worldwide.
This template is distributed without any warranty. See <http://creativecommons.org/publicdomain/zero/1.0/>.

[g8]: http://www.foundweekends.org/giter8/
