Git Remote
![[Pasted image 20260111105501.png]]

![[Pasted image 20260111105610.png]]

Common `git remote` Subcommands and Usage

The `git remote` command is typically used with various subcommands to manage these connections: 

|Command|
|---|

||Description|

|`git remote`|Lists the names of the remote repositories you have configured.|

|`git remote -v`|Lists the names and the corresponding URLs for the remotes (verbose mode).|

|`git remote add <name> <url>`|Adds a new remote repository connection. You can then use `<name>` as a shortcut for `<url>` in other Git commands (e.g., `origin`, `upstream`).|

|`git remote remove <name>`|Removes the specified remote connection from your local configuration.|

|`git remote rename <old> <new>`|Renames an existing remote connection from the `<old>` name to the `<new>` name.|

|`git remote show <name>`|Displays detailed information about a specific remote, including fetch and push URLs and associated branches.|

|`git remote get-url <name>`|Retrieves the URL(s) for a specific remote.|

|`git remote set-url <name> <newurl>`|Changes the URL for an existing remote.|

These remote configurations are crucial for synchronizing your work with others. Once configured, you use other commands to interact with them, such as `git fetch`, `git pull`, and `git push`.

# How to add a local repository in github
To link a local Git repository to a GitHub repository, you need to

==add the GitHub repository as a remote to your local one and then push your local commits==. This process assumes you have an existing local Git repository and a corresponding empty repository created on GitHub. 

Prerequisites

- You have a local directory initialized as a Git repository (`git init`).
- You have committed your local files (`git add .`, `git commit -m "Initial commit"`).
- You have created an **empty** repository on GitHub (do not initialize with a README, license, or .gitignore file to avoid merge conflicts).
- You have the HTTPS or SSH URL for your GitHub repository.
- You are authenticated to GitHub, ideally using a Personal Access Token (PAT) for HTTPS or SSH keys, as password authentication is deprecated. 

Steps to link the repositories

1. **Open your terminal or Git Bash** and navigate to the root directory of your local project.
2. **Add the GitHub repository as a remote** using the `git remote add` command. The conventional name for the primary remote is `origin`.
    
    bash
    

- ```
    git remote add origin <REMOTE_REPOSITORY_URL>
    ```
    
    Replace `<REMOTE_REPOSITORY_URL>` with the URL you copied from your GitHub repository's Quick Setup page.
- **Verify the remote URL** by running:
    
    bash
    
- ```
    git remote -v
    ```
    
    You should see the fetch and push URLs for your new `origin` remote.
- **Push your local commits to GitHub** using the following command. The `-u` flag sets the upstream branch, so future pushes only require `git push`.
    
    bash
    

```
git push -u origin main
```

- **Note:** If your local default branch is named `master`, replace `main` with `master` in the command above. 

Your local repository is now linked to your GitHub repository, and your code is pushed to the remote.