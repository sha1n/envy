# envy
This repo contains basic ansible playbooks for setting up development environments on macOS and Ubuntu (to my own preferences). 
Ubuntu support is limited to essential tools. 

Playbooks were tested with Ansible 2.11 on macOS and 2.9 on Ubuntu (see [Vagrantfile](testbox/Vagrantfile)).

- [envy](#envy)
  - [Install Ansible](#install-ansible)
  - [Play a playbook from source](#play-a-playbook-from-source)

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

## Play a playbook from source
```
# edit var files to your preferences
vi ./vars/user.yml

# run a playbook
./playbooks/dev.yml
```
