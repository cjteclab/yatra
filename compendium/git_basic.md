# GIT BASIC

## How to create a git repository and link it with an github repository by ssh-key

### Step 1 - Prepare Host
1. At your **host** create a new **directory** and initializing it with git (version control)
```bash
$ mkdir [directory]
$ cd [directory]
$ git init
```
### Step 2 - Checkout the **git config** or adjust it
1. Verify, if your git config is set
```bash
$ git config --global user.name
$ git config --global user.email
```
2. If not, add user.name and user.email
```bash
$git config --global user.name [username]
$git config --global user.email [mailaddress] 
```
3. Verify your git config again -> Step 2.1

### Step 3 - Prepare GitHub
At github create a new **repository**

### Step 4 - Setup **SSH key pair** on the **host**
1. Check if you already have an SSH key (home directory)
```bash
ls -al ~/.ssh
```
2. If not, create a new one (ed25519 is a secure and recommended key type)
```bash
ssh-keygen -t ed25519 -C [mailaddress]
```
3. You’ll be prompted to specify a file to save the key and a passphrase -> **OPTIONAL**
4. Add the SSH Key to the SSH Agent -> change the name of the key if not default
```bash
eval "$(ssh-agent -s)"
ssh-add ~/.ssh/id_ed25519
```

### Step 5 - Add SSH key to GitHub
1. Copy the SSH key to your clipboard
```bash
cat ~/.ssh/id_ed25519.pub
```
2. Add the key to github: user->settings->ssh and gpg keys
3. Enter your target repository and copy the **ssh remote url**

### Step 6 - Set **git remote url** on **host**
1. Change the url in your local Git repository
```bash
git remote set-url origin [git-remote-ssh-url]
```
2. Test the ssh connection
```bash
ssh -T git@github.com
```

### Step 7 - Push local repository to github
1. Use the push command
```bash
git push origin main
```

## How to change the standard editor in git
