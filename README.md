git-ghpull
==========

*Check out pull requests locally for testing and modification.*

Sure, maybe all the CI ran just fine on that PR, but you want to test something manually or make a small tweak before merging it.
This tool allows you to quickly check out the head of the PR and push back any changes (assuming the person filing the PR did not un-check the box allowing this).

Installation
------------

Install `git-ghpull` somewhere in PATH:

    sudo curl https://raw.githubusercontent.com/djmitche/git-ghpull/master/git-ghpull > /usr/bin/git-ghpull
    sudo chmod +x /usr/bin/git-ghpull

Usage
-----

This tool assumes that pull requests are against the GitHub  repo named by the `upstream` Git remote.
If necessary, add a new remote named `upstream`.
It's OK if that's the same as `origin`.

Then, to pull PR#1234:

    git ghpull 1234

This will create a new branch pointing to the head of PR#1234.

By default, this will use the same branch name as the pull request.
This is a requirement of git in order that `git push` will successfully push back to the same remote.
However, it will refuse to do so if the branch already exists, unless `-f` is given.

To instead create a branch named `pr1234`, use `-p`.
In this case, a bare `git push` will not automatically push changes back to the pull-request HEAD.
