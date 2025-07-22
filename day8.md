# Install Ansible

## Requirements

During the weekly meeting, the Nautilus DevOps team discussed about the automation and configuration management solutions that they want to implement. While considering several options, the team has decided to go with Ansible for now due to its simple setup and minimal pre-requisites. The team wanted to start testing using Ansible, so they have decided to use jump host as an Ansible controller to test different kind of tasks on rest of the servers.

- Install Ansible version 4.9.0 on Jump host using pip3 only. Make sure Ansible binary is available globally on this system, i.e all users on this system are able to run Ansible commands.

## Steps

- Install Python 3 and pip3 (if not already installed):
  ```console
  sudo dnf install -y python3
  ```
- Install Ansible globally
  ```console
  sudo pip3 install "ansible==4.9.0"
  ```
- Ensure the Ansible binary is globally accessible
  ```console
  which ansible
  ```
- Check the version; it should show 4.9.0
  ```console
  ansible --version
  ```
