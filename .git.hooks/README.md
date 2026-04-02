# Git Action Hooks

When certain git actions are attempted, a corresponding hook script is executed
(if it exists and is executable). If a `pre-` script fails (return non-zero
status) then the action is aborted.

For example, when `git commit` is invoked, first `.git/hooks/pre-commit` is
run, and if it fails then no changes are made to the repository.

The `run` script is a generic hook implementation; when run directly it will
install appropriate symlinks into `.git/hooks`.

It will invoke each of the test scripts in the subdirectory of `.git.hooks`
corresponding to the hook. Test scripts must be executable and have names that
start with a digit and end with a digit or letter; other files are ignored.
