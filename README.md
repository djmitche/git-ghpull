git-ghpull
==========

Merge pull requests qiuckly with a helpful merge message

Installation
------------

Install `git-ghpull` somewhere in PATH:

    sudo curl https://raw.githubusercontent.com/djmitche/git-ghpull/master/git-ghpull > /usr/bin/git-ghpull
    sudo chmod +x /usr/bin/git-ghpull

Usage
-----

First, configure things for the repository containing the pull requests:

    git config ghpull.username mozilla
    git config ghpull.reponame gecko-dev

Optionally, specify options for the `git pull` operation:

    git config ghpull.options "--no-commit"

Now, to merge pull request 1234, just:

    git ghpull 1234

Verify the results, then push back (well, commit first if you used `--no-commit`).
