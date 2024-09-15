# Experiment: Configuring `deptry` as a `pre-commit.ci` hook with `uv`

[![pre-commit.ci status](https://results.pre-commit.ci/badge/github/nathanjmcdougall/uv-precommit-deptry-test/main.svg)](https://results.pre-commit.ci/latest/github/nathanjmcdougall/uv-precommit-deptry-test/main) [![uv](https://img.shields.io/endpoint?url=https://raw.githubusercontent.com/astral-sh/uv/main/assets/badge/v0.json)](https://github.com/astral-sh/uv)

Conclusion: this would only work on `pre-commit.ci` lite 😢

Configuring [`deptry`](https://github.com/fpgmaas/deptry) with `pre-commit` is a little tricky since it needs to access the virtual environment to automatically determine the names of modules exposed by each distribution package. This is an experiment to see if `uv` can be used to set up the virtual environment from within a `python` language hook rather than `system`.

This would also have the added advantage that you don't need to pin the repo version for
`deptry` - it will just use the `uv` lockfile.

The reason this doesn't work is that `uv` doesn't get a chance to connect the to internet to download arbitary packages. `pre-commit.ci` firewalls things, presumably. Fair enough! In any case, this approach should still work with [`pre-commit.ci` lite](https://pre-commit.ci/lite.html), however the advantages to using a `python` language hook are less clear in that case (although it still probably makes things more robust by handling the virutal environment syncing and activation).
