---
description: This template guides the code agent through general server foundation development tasks. While the user specifies most steps, this template ensures adherence to standard procedures, like submitting pull requests to the appropriate upstream repository.
example: "egent_start: General task, adding a new feature to import-controller"
parameters:
  github_username:
    description: Your github username
dependencies:
  - knowledge/code/repos.md
  - knowledge/tools/git.md
  - knowledge/tools/github.md
---

- Identify which repository the user wants to work with based on their description
- Check if the repository exists in the current directory
- If not, clone the repo from `https://github.com/<current-github-user>/<repo-name>.git`; If repo is not forked from `stolostron`, please fork it first.
- Checkout to the main branch, if there are any uncommitted changes, stash them. Then sync the main branch with the upstream repository.
- Based on the user's description, perform development and testing
- If development and testing are successful, create a new branch with a name that is concise and reflects the content of this development
- Commit the code and push to the new branch
- Create a pull request
- Return the pull request link
