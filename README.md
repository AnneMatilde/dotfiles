# Anne Matilde's Dotfiles

This is a fork of [cobraz/dotfiles](https://github.com/cobraz/dotfiles).

## Setting up a new machine

With a new machine, you first have to install `Homebrew` and setup
[your SSH key](https://docs.github.com/en/free-pro-team@latest/github/authenticating-to-github/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent).
You can do that with this command:

```shell
▶ ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```

Next you need to clone this repository to your `$HOME` folder. Best practice is
to use `YADM` (a tool for managing dotfiles).

That is easily installed with brew, as such:

```shell
▶ brew install yadm
```

Then you need to clone this repository. You can read how to get started with
YADM under basics -> [Getting started](https://yadm.io/docs/getting_started).

Or, just type this in your terminal:

```shell
▶ yadm clone git@github.com:AnneMatilde/dotfiles.git
```

You should have all your files located in `$HOME` at this point. All you have to
do now is bootstrap! 🎉

```shell
▶ ./bootstrap.sh
```

To install the Mac OS defaults, run this command:

```shell
▶ ./.macos
```

## Append Brew packages

Step one is to find the package (software) you'd like to install and append to
the Dotfiles. You can search here: https://formulae.brew.sh/cask/

Next you should install that package on your current machine, like this:

```shell
brew install --cask spotify
```

To make sure you remember which packages you use, Open up `brew.sh`, e.g. with
VSCode as such:

```shell
▶ code ~/brew.sh
```

Append the link found on Brew Formulae to the list with `# Tooling` heading. We
use a `Brewfile`, so the entries in this files look like this:

`brew "spotify"`

## Update your dotfiles

Check which files have been changed with:

```shell
▶ yadm status
```

If there is any changes, run these commands:

```shell
▶ yadm commit -a -m "<your description">
▶ yadm push
```
