# Linux User Setup with Non-Interactive Shell 

## Requirement
- The task is to create a user named `rose` with a non-interactive shell

## Steps
- Add a user with the option of a non-interactive shell
```console
sudo useradd -s rose /sbin/nologin
```
