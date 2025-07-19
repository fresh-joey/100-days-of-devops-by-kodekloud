# Secure Root SSH Access
Following security audits, the xFusionCorp Industries security team has rolled out new protocols, including the restriction of direct root SSH login.

## Requirement
Your task is to disable direct SSH root login on all app servers within the Stratos Datacenter.

## Steps
- SSH into the server
```console
ssh tony@<app_server_IP>
```
- Run the command below to modify the SSH configurations
```console
sudo vi /etc/ssh/sshd_config
```
- Look for the line `PermitRootLogin yes`
- Change it to `PermitRootLogin no`
- Restart the Server
```console
sudo systemctl restart sshd
```
- Verify the configuration by trying to SSH into the server with the root user
