# envy
This repo contains basic ansible playbooks I use to set up development and test environments on macOS and Ubuntu.
Ubuntu support is limited and focused on terminal configuration. I use it primarily to set up virtual test boxes.

Playbooks were tested with Ansible 2.11 on macOS and 2.9 on Ubuntu (see [Vagrantfile](testbox/Vagrantfile)).

- [envy](#envy)
  - [Install Ansible](#install-ansible)
  - [Running from source](#running-from-source)
  - [Roles overview](#roles-overview)

## Install Ansible
**macOS**
```
# install ansible
brew install ansible
```

**Ubuntu**
```
sudo apt update
sudo apt install -y software-properties-common
sudo add-apt-repository --yes --update ppa:ansible/ansible
sudo apt install -y ansible

# install ansible 'community.general' collection
ansible-galaxy collection install community.general
```

## Running from source

```bash
git clone git@github.com:sha1n/envy.git
cd envy

# To avoid prompts either edit 'vars/user.yml' to your preferences or use --extra-vars="<name>=<valu>" 

# run a playbook straight 
playbooks/essentials.yml
# run selectively with tags
playbooks/dev.yml -t vscode -t go
```

## Roles overview
The roles included in this repo are designed around my preferences and are not always properly generalized for reuse. However, in most case they can very easily be moded to serve other needs.

- git
  - installs git
  - `.gitconfig`
  - global ignore file
- go (macOS)
  - installs golang
  - sets-up shell environment
- nvm (macOS)
  - installs nvm
  - sets-up shell environment
- brew_setup
  - installs homebrew
- brew
  - generic role that installs brews and casks based on variables
- bazel
  - installs `bazelisk` 
  - installs bazel build tools
  - installs a `.bazelrc` 
- shell 
  - installs my personal [zsh profile settings](https://github.com/sha1n/profile)
  - powerline fonts (macOS)
  - vim + solarized.vim colors (macOS)
  - basic nvim setup (macOS)
  - fzf (macOS)
- vscode (macOS)
  - installs vscode
  - installs vscode plugins
