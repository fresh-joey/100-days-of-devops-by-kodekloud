# Create a cronjob

The Nautilus system admins team has prepared scripts to automate several day-to-day tasks. 
They want them to be deployed on all app servers in Stratos DC on a set schedule. 
Before that they need to test similar functionality with a sample cron job. 
Therefore, perform the steps below:

## Requirement
a. Install cronie package on all Nautilus app servers and start crond service.
b. Add a cron */5 * * * * echo hello > /tmp/cron_text for root user.

## Steps 
- SSH into the server
- Install cronie
  ```shell
  Sudo dnf install cronie
  ```
- Enable and start the service
  ```shell
  sudo systemctl enable crond
  sudo systemctl start crond
  ```
- Add schedule to cron
  ```shell
  crontab -e
  ```
- Put the details as required
  ```ini
  */5 * * * * echo hello > /tmp/cron_text
  ```

  - Repeat the above steps for all the servers
