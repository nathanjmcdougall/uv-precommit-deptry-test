# Configuring `deptry` as a `pre-commit.ci` hook with `uv`

[![pre-commit.ci status](https://results.pre-commit.ci/badge/github/nathanjmcdougall/uv-precommit-deptry-test/main.svg)](https://results.pre-commit.ci/latest/github/nathanjmcdougall/uv-precommit-deptry-test/main) [![uv](https://img.shields.io/endpoint?url=https://raw.githubusercontent.com/astral-sh/uv/main/assets/badge/v0.json)](https://github.com/astral-sh/uv)

Configuring [`deptry`](https://github.com/fpgmaas/deptry) with `pre-commit` is a little tricky since it needs to access the virtual environment to automatically determine the names of modules exposed by each distribution package. This is an experiment to see if `uv` can be used to set up the virtual environment from within a `python` language hook rather than `system`.

This also has the added advantage that you don't need to pin the repo version for
`deptry` - it will just use the `uv` lockfile.
