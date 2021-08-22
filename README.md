# envy
An ansible based macOS development environment setup tool (limited Ubuntu support).

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

## Run from source
```
# run a playbook
./playbooks/<playbook-name>.yml
```

## Run using ansible-pull
```
ansible-pull -U git@github.com:sha1n/envy.git playbooks/<playbook-name>.yml
```