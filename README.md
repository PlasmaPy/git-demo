# Contributing to an open source project

## Ahead of time

Please [**sign up for a GitHub account**](https://github.com/signup).

To follow along on **Windows**, please [install Windows Subsystem for Linux](https://learn.microsoft.com/en-us/windows/wsl/install#install-wsl-command) (WSL)
by running the following command in _PowerShell_ or _Windows Command Prompt_ in administrator mode:
`wsl --install`

To follow along on **macOS**, please [install git](https://github.com/git-guides/install-git#install-git-on-mac). (Note: To enter commands in a terminal: open _Finder_, go to _Applications_, enter the _Utilities_ folder, and open _Terminal_.)

To follow along on **Linux**, please follow these instructions to install git: https://github.com/git-guides/install-git#install-git-on-linux

## Getting ready to contribute

### Opening a terminal

 - macOS: _Finder_ → Applications → Utilities → Terminal
 - Windows: Use the start menu item for Windows Subsystem for Linux or WSL
 - Linux: ctrl + alt + T

### Optionally configuring `git`

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
have to take some extra steps for security. 
It's rather annoying, but typically need to be done once per computer. 

Please follow the instructions (which depend on the operating system) at: 

 - [Generate a new SSH key](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent), and

 - [Add the SSH key to your GitHub account](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/adding-a-new-ssh-key-to-your-github-account?platform=linux&tool=webui).


#### Adding an SSH key on Linux, CoCalc, and (probably) WSL

> [!NOTE]
> Use the links above to set up an SSH key on macOS or Windows, unless using WSL. 

1. Run the following command, _changing your email address_ to the one 
   associated with your GitHub account.

   ```bash
   ssh-keygen -t ed25519 -C "your-email@domain.com" -f ~/.ssh/id_ed25519 -N ""
   ```
   
2. Next run: 
   ```bash   
   eval "$(ssh-agent -s)"
   ssh-add ~/.ssh/id_ed25519
   ```

3. **Copy** the contents of the file `~/.ssh/id_ed25519.pub`.  
   In a Unix terminal, the command `cat` (short for "concatenate")
   prints out the contents of a file.

   ```bash
   cat ~/.ssh/id_ed25519.pub
   ```
   
4. Go to https://github.com/settings/profile
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
5. In a terminal, type `git clone` followed by a space and then paste the text that you copied.
   The command should be like:
   ```bash
   git clone git@github.com:your-github-username/git-demo.git
   ```

### Set up remotes

A **remote** is the address of a repository hosted on GitHub. 
The most common convention is to define:
 - `upstream` as the primary repository
 - `origin` as our fork of the repository 

1. Define the primary repository as the `upstream` remote 
   ```bash
   git remote add upstream git@github.com:PlasmaPy/git-demo.git
   ``` 
   
2. To verify that the remotes have been entered correctly, type:
   ```bash
   git remote -v
   ```
   This should display four lines, with `origin` pointing to your fork
   and `upstream` pointing to the primary repository.

## Code contribution workflow   

### Create a branch and connect it to GitHub

1. Update our clone so that it knows the current state of the primary and forked repositories:
   ```bash
   git fetch --all
   ```
   
2. Next, create a 
   [branch](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/about-branches)
   to make our changes in, and immediately switch to it. 
   We can change `feature-branch` to a more descriptive name.
   ```bash
   git checkout -b feature-branch upstream/main 
   ```
 
   > [!NOTE]
   > A branch is a separate/isolated version of a project.
   > Using branches lets us make an independent and isolated set of changes. 
   > These changes later _merge_ back into the `main` branch.

3. We created a branch on our computer. 
   Next we need to link that branch to GitHub.
   ```bash
   git push --set-upstream origin feature-branch 
   ```

## Adding, committing, and pushing changes

1. Edit a file and save the changes.
   In a Unix shell, we can create a blank file with `touch`:
   ```bash 
   touch file1.txt
   ```
   
2. To line up the changes that we want to record as a snapshot in history, run: 
   ```bash 
   git add file1.txt
   ```
   This step is like putting items in a box that we want to mail.

3. To **commit** the changes (and preserve a snapshot of what each file looks like at this time in history), run:
   ```bash
   git commit -m "Add blank file1.txt"
   ```
   The `-m` is short for `--message`. We use the commit message — the 
   text in quotes — to describe the changes that we made.
   This step is like closing the box and putting it in outgoing mail.

4. After one or more commits, send (push) the changes to GitHub.
   ```bash
   git push
   ```
   This step is like mailing a box to GitHub.

## Making a pull request

We're almost there!

1. Go to https://github.com/PlasmaPy/git-demo.git
2. There will be a banner that says something like "Make pull request". Click on it.
3. Add a title like "Add blank file" and (optionally) a description.
4. Click on submit pull request.  
5. Congratulations!
