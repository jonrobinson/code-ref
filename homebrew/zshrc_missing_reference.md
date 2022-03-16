# Fixing a missing reference in zshrc

### Example Issue: "zsh: command not found: nvm" even though already installed with Homebrew
Reference: https://code2care.org/q/zsh-command-not-found-nvm-brew-macos
Overall you will want to:
1. find where it is installed by brew
2. and reference the .sh file in `.zshrc`
3. restart .zshrc
4. test

### Step 1: Find where it's installed
```
brew --prefix nvm
```
Response:
```
/usr/local/opt/nvm
```

### Step 2: Reference the .sh file in the .zshrc
```
vim ~/.zshrc
```
Add the following
1. the brew prefix
2. append "your-example.sh"
```
export NVM_DIR="$HOME/.yourexample"
. "/your-brew-prefix-folders/yourexample.sh"
```

For example:
```
export NVM_DIR="$HOME/.nvm"
. "/opt/homebrew/opt/nvm/nvm.sh"
```

### Step 3: Restart
```
source ~/.zshrc
```

### Step 4: Test
```
nvm list
```
