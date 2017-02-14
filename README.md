# Minimal git hooks installer

This is a very minimal installation of git hooks in git repositories.

Currently, only pre-commit hooks are supported and each hook can be enabled/disabled at install time.

## Installation

Clone this repository, for example in your ~/.git-hooks.

```
git clone git@github.com:colinux/.git-hooks.git
```

Make `install-hooks` file executable :

```
chmod +x ~/.git-hooks/install-hooks
```

## Usage

To install the hooks in a repository, run `install-hooks` from this repository :

```
cd /path/to/git/repository
~/.git-hooks/install-hooks
```

You'll be prompted for each hook to install it or not. They are installed in `repository/.git/hooks/` directory.


## Pre-commit hooks

Each time you'll run `git commit`, the following hooks, if installed, will be executed. The commit will be avoided if one of them fail.

If you want to bypass the hooks run `git commit --no-verify`.


### no\_commit\_on\_master

In most of projects, you never want commit on master.

### rubocop

In a ruby project, if you're using `rubocop`, abort a commit if an offense is found.

You need to have a `.rubocop.yml` config file and the `rubocop` gem listed in your `Gemfile`.


## LICENSE

Licensed under the MIT license, see [LICENSE](/LICENSE) file.
