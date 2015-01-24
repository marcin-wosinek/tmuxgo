# tmuxgo
Simple scritp to start predefined tmux nested session

# Installation
Clone the repository link to tmuxgo from a folder you have in the path variable.

# Session description

Describe your session in json format. Main object defines the session, each
object in *open* array defines widows.

# Flat tmux session

```json
{
  "name": "project",
  "location": "~/workspace/project",
  "open": [
    {
      "name": "git"
    },
    {
      "name": "vim",
      "open": "vim"
    },
    {
      "name": "grunt",
      "open": "grunt serve"
    },
    {
      "name": "zsh"
    }
  ]
}
```

# Flat tmux session

```json
{
  "name": "main",
  "location": "~/workspace",
  "open": [
    {
      "name": "project",
      "location": "<relative location",
      "open": [
        ...
      ]
    },
    ...
  ]
}
```

# Starting session

To start the session:

```bash
$ tmuxgo session.json
```
