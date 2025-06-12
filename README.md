# latex.slides.g8

__TODO:__ Update this README file to reflect what I actually did here...

Unofficial, opinionated [Giter8][g8] template for latex beamer slides,
using the [Metropolis](https://github.com/matze/mtheme) theme for Beamer.

## How to Create a New Project Using Giter8

If `g8` is installed on your machine (see the next section for more on
`g8` installation), you can create a new slides project by running:
```bash
g8 jerrykuch/latex.slides.g8
```
and filling out the requested fields to generate your project
skeleton.   What you enter for `name` will be used as the folder name (a
new folder will be created if not present), `title` will be used for the slide
deck's title (you can edit the title later), and so on.

You can also  generate a new project from a local clone of the repo
you're currently looking at by using `g8` as follows:
```
g8 file:///<local-checkout-dir>/latex.slides.g8/ --name=<name> --title=<title> --author=<project author> --force
```
The above also demonstrates using command line parameters to
pre-answer some of the questions `g8` would otherwise ask you.

For more details on using `g8`, look [here](http://www.foundweekends.org/giter8/usage.html#Usage).

## How to Create a New Project Using `sbt`

If you don't have 'g8' installed, by you do have `sbt` on your
machine, you can do the following:
```bash
sbt new jerrykuch/latex.slides.g8 --name=<name> --title=<title> --author=<project author> --force
```
Or, from a local clone of the repo (be careful to pull the latest
changes locally before running the command):
```bash
sbt new file:///<local-checkout-dir>/latex.slides.g8 --name=<name> --title=<title> --author=<project author> --force
```

For more options, refer to the original documentation in
https://www.scala-sbt.org/ and
http://www.foundweekends.org/giter8/setup.html respectively.

## Installing Giter8

On MAC OS X, both `sbt` and `giter8` are available via the Homebrew
package manager:
```
brew update
brew install giter8
brew install sbt
```

## License

__TODO:__ Add one here.

