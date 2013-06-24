# Git (and Stash) code review checklist

## Line wrapping

Use [hard line wrapping](http://stopwritingramblingcommitmessages.com/) in your commit messages. [The maximum line length should be 72 characters](http://tbaggery.com/2008/04/19/a-note-about-git-commit-messages.html) unless there is some reason it can't be. Vim will automatically insert line breaks as you type if you use it as your commit message editor, which you can configure by running `git config --global core.editor "vim"`. To fix this commit, you can amend it, and when the commit message opens in Vim, use the command "`gq`" on each line that is too long.

## Are there more commits than there ought to be?

...

### Are the extra commits changes arising from code review?

...

### How to squash (two commits into one)

* Check out this branch.
* Do an interactive rebase: `git rebase -i HEAD^^`
* Git opens the editor to ask what you want to do with these two commits. On the second line, replace `pick` with `squash`.
* Save/quit the editor.
* Git opens the editor again to prompt you for the commit message for the new squashed commit. It conveniently starts you with the messages for all of the commits being squashed. Combine them into one message.
* Push with the `force` flag to rewrite history: `git push --force`
* Stash will update the pull request (although it won't update until you reopen it).
