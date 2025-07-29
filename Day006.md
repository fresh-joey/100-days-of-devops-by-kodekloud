# Create a cron job

The Nautilus system admins team has prepared scripts to automate several day-to-day tasks. 
They want them to be deployed on all app servers in Stratos DC on a set schedule. 
Before that, they need to test similar functionality with a sample cron job. 
Therefore, perform the steps below:

## Requirement
a. Install the cronie package on all Nautilus app servers and start the crond service.
b. Add a cron */5 * * * * echo hello > /tmp/cron_text for root user.

## Steps 
- SSH into the server
- Install cronie
  ```console
  Sudo dnf install cronie -y
  ```
- Enable and start the service
  ```console
  sudo systemctl enable crond
  sudo systemctl start crond
  ```
- Add a cron job for the root user
  ```console
  sudo crontab -u root -e
  ```
- Put the details as required
  ```ini
  */5 * * * * echo hello > /tmp/cron_text
  ```
- Check if a cron job is created for the root user in the cron directory
  ```console
  sudo ls /var/spool/cron
  ```
- Repeat the above steps for all the servers
