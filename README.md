# Contributing to an open source project

## Ahead of time

Please [**sign up for a GitHub account**](https://github.com/signup).

To follow along on **Windows**, please [install Windows Subsystem for Linux](https://learn.microsoft.com/en-us/windows/wsl/install#install-wsl-command) (WSL)
by running the following command in _PowerShell_ or _Windows Command Prompt_ in administrator mode:
`wsl --install`

To follow along on **macOS**, please [install git](https://github.com/git-guides/install-git#install-git-on-mac).  
(Note: To enter commands in a terminal: open _Finder_, go to _Applications_,
enter the _Utilities_ folder, and open _Terminal_.)

To follow along on Linux, please follow these instructions to install git: https://github.com/git-guides/install-git#install-git-on-linux

## Getting ready to contribute

### Open a terminal

### Optionally configure `git`

We can assign ourselves as the author of changes with the following command
— making sure to change "Your Name" to your name!

```bash
git config --global user.name "Your Name"
```

We can optionally provide an email address that will show up in the 
`git` history.  

```bash
git config --global user.email "your.email@example.com"
```

### Add a new SSH key to your GitHub account

GitHub made its authentication process more strict in 2023, so now we 
have to take some extra steps to make changes to a GitHub repository
locally. 

1. Open a terminal.
   - macOS: In the "Finder, go to _Applications_. Enter the _Utilities_
     folder and then _Terminal_.
   - Windows: open WSL

2. Run the following commands, changing your email address to the one 
   associated with your GitHub account.

   ```bash
   ssh-keygen -t ed25519 -C "your-email@domain.com" -f ~/.ssh/id_ed25519 -N ""
   ```
   
3. Run the following commands:  
   ```bash   
   eval "$(ssh-agent -s)"
   ssh-add ~/.ssh/id_ed25519
   ```

4. **Copy** the contents of the file `~/.ssh/id_ed25519.pub`.  
   In a Unix terminal, we can use the command `cat` (short for "concatenate")
   which will print out the contents of a file.

   ```bash
   cat ~/.ssh/id_ed25519.pub
   ```
   
5. to https://github.com/settings/profile
   - In the "Access" section of the sidebar, click on "SSH and GPG keys"
   - Enter a descriptive title like "home laptop"
   - Click _New SSH key_ or _Add SSH key_
   - In the _Key_ field, **paste** what was copied in the previous step.
   - Click _Add SSH key_.  

## Initial setup

### Forking the repository

We can **fork** a repository to make our own copy of it on GitHub.

1. [Log in to GitHub](https://github.com/login).
2. Go to: https://github.com/PlasmaPy/git-demo
3. Towards the upper right, click on the **Fork** button.
4. In the lower right, click on **Create Fork**.

### Cloning the repository

1. Go to your fork of the repository
2. Click on the green button that says "<> Code ▼"
3. Select the SSH tab
4. Click on the copy button "⧉"
5. Open a terminal.
6. Type `git clone` followed by a space and then paste the text that you copied.
   The command should be like:
   ```bash
   git clone git@github.com:your-github-username/git-demo.git
   ```

### Set up remotes

1. Enter the command:
   ```bash
   git remote add upstream git@github.com:PlasmaPy/git-demo.git
   ``` 
   
2. To verify that the remotes have been entered correctly, type:
   ```bash
   git remote -v
   ``` 
   
## Create a branch and connect it to GitHub

1. Enter
   ```git fetch --all```
   
2. Enter
   ```bash
   git checkout -b feature-branch upstream/main 
   ```

3. Enter
   ```bash
   git push --upstream feature-branch 
   ```

## Making changes

1. Add a new file named `file.txt`.
   In a Unix terminal, we can do this by 
   ```bash 
   touch file1.txt
   ```
   
2. Put it in the staging area
   ```bash 
   git add file1.txt
   ```

3. Now commit it
   ```bash
   git commit -m "Add blank file1.txt"
   ```
   
4. Push it to GitHub
   ```bash
   git push
   ```

## Making a pull request

1. Go to https://github.com/PlasmaPy/git-demo.git
2. There will be a banner that says something like "Make pull request". Click on it.
3. Add a title like "Add blank file" and (optionally) a description.
4. Click on submit pull request.  
5. Congratulations!
