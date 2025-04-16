# Contributing to an open source project

## Ahead of time

If you would like to follow along with the tutorial, 
please [**sign up for a GitHub account**](https://github.com/signup).

### Following along on Windows

If you are on **Windows**, please install Windows Subsystem for Linux (WSL)
by running the following command in PowerShell or Windows Command Prompt:

```powershell
wsl --install
```

Go to the 

### Following along on macOS

## Getting ready to contribute

### Configure `git`

```bash
git config --global user.name "Your Name"
```

```bash
git config --global user.email "your.email@example.com"
```

### Add a new SSH key to your GitHub account

GitHub made its authentication process more strict in 2023, so now we 
have to take some extra steps to make changes to a GitHub repository
locally.

1. Open a terminal.
   - macOS: In the "Finder, go to _Applications_. Enter the _Utilities_ folder and then _Terminal_.
   

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

1. [Log in to GitHub](https://github.com/login).
2. Go to this GitHub repository.
3. Towards the upper right, there's a button called **Fork**
4. 



 