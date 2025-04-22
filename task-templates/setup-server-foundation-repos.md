---
name: Setup Server Foundation Repos
description: Setup the server foundation repos.
example: "egent: setup server foundation repos, github username: zxue"
parameters:
  github_username:
    description: Your github username
dependencies:
  - knowledge/code/repos.md
  - knowledge/tools/git.md
  - knowledge/tools/github.md
---

Actions:

- create a new directory named `workplace` if it doesn't exist
- get the list of server foundation repos
- for each repo, clone it to the `workplace` directory, NOTE!!! Always clone the forked repo in your github account{{github_username}}, NOT the upstream repo.
