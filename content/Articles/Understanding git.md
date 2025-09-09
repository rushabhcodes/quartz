---
created: 2025-09-09T11:06
updated: 2025-09-09T12:00
---
# Initializing a git repo

When we run the command `git init` it creates a `.git`  directory.
```bash
git init
Initialized empty Git repository in /home/rushabh/test/.git/
```
## Peeking Inside the .git Folder

```bash
ls .git
 config   description   HEAD   hooks   info   objects   refs
```


Based on my research, here's a short, line-by-line explanation of the files and folders i found.

- **`config`**: This file stores your repository's specific settings, like the URLs of remote repositories and other project-level configurations.

- **`description`**: This is a simple, human-readable file primarily used by GitWeb, a web-based repository browser.

- **`HEAD`**: This file acts as a pointer to the current commit you're working on. It tells Git what your current position is in the project's history.

- **`hooks`**: This directory contains scripts that can be triggered automatically at specific points in the Git workflow, such as before a commit.

- **`info`**: This folder holds information that is not part of the committed repository, such as a private `.gitignore` file (`exclude`) for your local use.

- **`objects`**: This is where Git stores your project's data. Every file, commit, and snapshot is saved here as a compressed object.

- **`refs`**: This directory holds pointers to commits, known as references. It's where your branches and tags are stored.
### Hears a more detailed look in the contents of .git directory

```bash
$ tree .git                                                                      

.git
├── config
├── description
├── HEAD
├── hooks
│   ├── applypatch-msg.sample
│   ├── commit-msg.sample
│   ├── fsmonitor-watchman.sample
│   ├── post-update.sample
│   ├── pre-applypatch.sample
│   ├── pre-commit.sample
│   ├── pre-merge-commit.sample
│   ├── prepare-commit-msg.sample
│   ├── pre-push.sample
│   ├── pre-rebase.sample
│   ├── pre-receive.sample
│   ├── push-to-checkout.sample
│   ├── sendemail-validate.sample
│   └── update.sample
├── info
│   └── exclude
├── objects
│   ├── info
│   └── pack
└── refs
    ├── heads
    └── tags
```

From all these files and folders, the `objects` directory is the most important one.

# Git Objects
