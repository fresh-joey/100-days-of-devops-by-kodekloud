#  Linux SSH Authentication

## Requirements
The system admins team of xFusionCorp Industries has set up some scripts on jump host that run on regular intervals and perform operations on all app servers in Stratos Datacenter. To make these scripts work properly we need to make sure the thor user on jump host has password-less SSH access to all app servers through their respective sudo users (i.e tony for app server 1). Based on the requirements, perform the following:
- Set up a password-less authentication from user thor on jump host to all app servers through their respective sudo users.

## Steps
- This requires the use of SSH keys to sign in. A public and private key pair will be generated.
- Generate SSH keys. You can save the keys with a custom name or accept the default when prompted
  ```console
  ssh-keygen -t rsa -b 4096 -C tony
  ```
- Using the -C flag when generating the keys ensures that the key can be easily identified with the tag, which could be an email or username.
- Copy keys to server
  ```console
  ssh-copy-id user@server-ip
  ```
- SSH into the server and check to be sure the right key was copied
- Then connect with the user and hostname of the server
  ```console
  ssh tony@stapp01
  ```
