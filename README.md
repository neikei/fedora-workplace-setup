# fedora-workplace-setup

[fedora](https://getfedora.org/) workplace setup with ansible.

## Installation

```bash
# 1. Install ansible
sudo dnf install ansible

# 2. Download the install.yml
wget https://raw.githubusercontent.com/neikei/fedora-workplace-setup/master/install.yml

# 3. Run the installation
ansible-playbook install.yml --ask-become-pass
```

## Included software

```yaml
    dnf_packages:
      - chromium
      - geary
      - git
      - gnome-tweaks
      - keepassxc
      - lsof
      - nmap
      - nmon
      - tree
      - vagrant
      - vim
#      - pdfsam # Not available
    snap_packages:
      - name: "spotify"
        classic: "no"
      - name: "signal-desktop"
        classic: "no"
      - name: "code"
        classic: "yes"
      - name: "sublime-text"
        classic: "yes"
    unneeded_packages:
      - ""
    install_vbox: false # Missing repo for Fedora 32
```
