# Configuring `deptry` as a `pre-commit.ci` hook with `uv`

Configuring `deptry` with `pre-commit` is a little tricky since it needs to access the
virtual environment to automatically determine the names of modules exposed by each
distribution package. This is an experiment to see if `uv` can be used to set up the
virtual environment from within a `python` language hook rather than `system`.

This also has the added advantage that you don't need to pin the repo version for
`deptry` - it will just use the `uv` lockfile.
