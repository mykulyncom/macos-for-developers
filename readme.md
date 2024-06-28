# macOS for web developers

## Table of contents
* [iTerm2](#iterm2)
* [GIT](#git)
* [SlimZSH](#slimzsh)
* [NVM](#nvm)
* [Node.js](#nodejs)
* [Yarn](#yarn)
* [TypeScript](#typescript)
* [PNPM](#pnpm)
* [Homebrew](#homebrew)
* [PHP](#php)
* [Composer](#composer)

## iTerm2
[Download iTerm2 ↗️](https://iterm2.com)

## GIT
Git is a distributed version control system that tracks changes in any set of computer files, usually used for coordinating work among programmers who are collaboratively developing source code during software development. Its goals include speed, data integrity, and support for distributed, non-linear workflows (thousands of parallel branches running on different computers).
#### Settings git
```bash
git config --global user.name "Your Full Name"
git config --global user.email "youremail@gmail.com"
git config --global init.defaultBranch main
```
#### Settings SSH
```bash
ssh-keygen
cat ~/.ssh/id_rsa.pub
```
Insert on this page https://github.com/settings/ssh/new

## SlimZSH
A small, usable configuration for ZSH. It enables all the awesomeness of ZSH with a small and tidy config. https://github.com/changs/slimzsh
```bash
git clone --recursive https://github.com/changs/slimzsh.git ~/.slimzsh
```
Add to `nano ~/.zshrc`
```bash
source "$HOME/.slimzsh/slim.zsh"
```
Restart terminal

## NVM
nvm is a version manager for node.js, designed to be installed per-user, and invoked per-shell. nvm works on any POSIX-compliant shell (sh, dash, ksh, zsh, bash), in particular on these platforms: unix, macOS, and windows WSL. https://github.com/nvm-sh/nvm
```bash
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.7/install.sh | bash
```
Add to `nano ~/.zshrc`
```bash
export NVM_DIR="$([ -z "${XDG_CONFIG_HOME-}" ] && printf %s "${HOME}/.nvm" || printf %s "${XDG_CONFIG_HOME}/nvm")"
[ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh" # This loads nvm
```
Restart terminal

## Node.js
https://nodejs.org/en
### Use nvm to manage Node.js versions

```bash
# Install or use the LTS version
nvm install --lts
nvm use --lts

# Install or use the latest version
nvm install node
nvm use node

# Install or use a specific version
nvm install <version>
nvm use <version>

# Show installed versions
nvm list

# Uninstall a Node.js version
nvm uninstall <version>
```

## Yarn
[Yarn](https://yarnpkg.com) is a package manager that doubles down as project manager. Whether you work on simple projects or industry monorepos, whether you're an open source developer or an enterprise user, Yarn has your back.
```bash
npm install --global yarn
```

### Use yarn
```bash
# Starting a new project
yarn init

# Installing all the dependencies of project
yarn
yarn install

# Adding a dependency
yarn add <package>

# Adding a dependency to devDependencies
yarn add -D <package>

# Upgrading a dependency
yarn upgrade <package>

# Removing a dependency
yarn remove <package>

# Generates a lock file entry.
yarn generate-lock-entry
```

## TypeScript

```bash
npm install --global typescript
```

## PNPM

```bash
npm install --global pnpm
```

## Homebrew
[Homebrew](https://brew.sh/) is a free and open-source software package management system that simplifies the installation of software on Apple's operating system, macOS, as well as Linux.

```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```
```bash
(echo; echo 'eval "$(/opt/homebrew/bin/brew shellenv)"') >> /Users/USERNAME/.zprofile
eval "$(/opt/homebrew/bin/brew shellenv)"
```

## PHP

### Install php
```bash
brew install php@8.1
brew install php@8.2
brew install php@8.3
```

### Choose PHP version
```bash
brew unlink php@8.1
brew link php@8.3
```

## Composer
[Composer](https://getcomposer.org/) is an application-level dependency manager for the PHP programming language that provides a standard format for managing dependencies of PHP software and required libraries.
```bash
php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');"
```
```bash
HASH=`curl -sS https://composer.github.io/installer.sig`
```
```bash
php -r "if (hash_file('SHA384', 'composer-setup.php') === '$HASH') { echo 'Installer verified'; } else { echo 'Installer corrupt'; unlink('composer-setup.php'); } echo PHP_EOL;"
```
```bash
sudo php composer-setup.php --install-dir=/usr/local/bin --filename=composer
```
