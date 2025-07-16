# Restrict Linux Server root SSH login

Following security audits, the xFusionCorp Industries security team has rolled out new protocols, including the restriction of direct root SSH login.
Your task is to disable direct SSH root login on all app servers within the Stratos Datacenter.

## Solution

- Login to the server
```shell
ssh tony@<app_server_IP>
```
- Run the command below
```shell
sudo vi /etc/ssh/sshd_config
```
- Look for the line `PermitRootLogin yes`
- Change it to `PermitRootLogin no`
- Restart the Server
```shell
sudo systemctl restart sshd
```
- Verify the configuration by trying to ssh into the server with root user
