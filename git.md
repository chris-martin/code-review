# Git code review checklist

## Line wrapping

Does the commit message have **long lines** (exceeding 72 characters per line)?

> Use [hard line wrapping](http://stopwritingramblingcommitmessages.com/) in your commit messages.
  [The maximum line length should be 72 characters]
  (http://tbaggery.com/2008/04/19/a-note-about-git-commit-messages.html)
  unless there is some reason it can't be.
  Vim will automatically insert line breaks as you type if you use it as your commit message editor,
  which you can configure by running `git config --global core.editor "vim"`.
  To fix this commit, you can amend it, and when the commit message opens in Vim, type "`ggVGgq`".
