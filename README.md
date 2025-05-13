# How to use

Open a empty directory, and run the following command:

Add the following mcp server to your code agent tool:

```json
{
  "mcpServers": {
    "egent": {
      "command": "npx",
      "args": [
        "-y",
        "egent@latest",
        "--playbook-repo",
        "git@github.com:stolostron/server-foundation-agent-playbook.git"
      ]
    }
  }
}
```

Chat with the agent:

```
egent: setup up all server foundation repos, my github username is {your github username}
```

You will see the agent creates the `workplace` directory, and clone the repos you need.

# Contributing

```shell
git clone git@github.com:stolostron/server-foundation-agent-playbook.git
```

Use `--context-path` to point to the path of the server-foundation-agent-playbook repo.

```json
{
  "mcpServers": {
    "egent-dev": {
      "command": "npx",
      "args": [
        "-y",
        "egent@latest",
        "--playbook-path",
        "<the path to the server-foundation-agent-playbook repo>"
      ]
    }
  }
}
```
