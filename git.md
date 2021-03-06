# Git (and Stash) code review checklist

Follow [this convention](http://tbaggery.com/2008/04/19/a-note-about-git-commit-messages.html) for commit messages: The first line should be a very brief summary (try to limit it to 50 characters), the second line should be blank, and the rest of the message should be hard-wrapped at 72 characters.

## No line wrapping

Use [hard line wrapping](http://stopwritingramblingcommitmessages.com/) in your commit messages. The first line should be a very brief summary, the second line should be blank, and for the rest of the message [the maximum line length should be 72 characters](http://tbaggery.com/2008/04/19/a-note-about-git-commit-messages.html) unless there is some reason it can't be.

Vim will automatically insert line breaks as you type if you use it as your commit message editor, which you can configure by running `git config --global core.editor "vim"`. To fix this commit, you can amend it, and when the commit message opens in Vim, use the command "`gq`" on each line that is too long.

## Wrapped summary line

Don't wrap the commit message summary line. The second line of the commit message should always be blank. If it's too long, then write a shorter summary instead, and move the details into the body of the commit message.

## Are there more commits than there ought to be?

...

### Are the extra commits changes arising from code review?

In the situation wherein you have a single-commit pull request and you're make changes in response to code review comments, usually you should modify that commit instead of adding another one. The first commit is not valuable to keep in the repository, and it adds needless clutter to the history. To edit your most recent commit instead of adding a new commit, use `git commit --amend` instead of `git commit`. After you do this, you'll need to force push because you're rewriting history on the remote: `git push --force`.

### How to squash (two commits into one)

* Check out this branch.
* Do an interactive rebase: `git rebase -i HEAD^^`
* Git opens the editor to ask what you want to do with these two commits. On the second line, replace `pick` with `squash`.
* Save/quit the editor.
* Git opens the editor again to prompt you for the commit message for the new squashed commit. It conveniently starts you with the messages for all of the commits being squashed. Combine them into one message.
* Push with the `force` flag to rewrite history: `git push --force`
* Stash will update the pull request (although it won't update until you reopen it).
