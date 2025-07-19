# SElinux Installation and Configuration

Following a security audit, the xFusionCorp Industries security team has opted to enhance application and server security with SELinux. \
To initiate testing, the following requirements have been established for App server 2 in the Stratos Datacenter:

## Requirements
- Install the required SELinux packages.
- Permanently disable SELinux for the time being; it will be re-enabled after necessary configuration changes.
- No need to reboot the server, as a scheduled maintenance reboot is already planned for tonight.
- Disregard the current status of SELinux via the command line; the final status after the reboot should be disabled.

## Steps
- SSH into the server
- Install the required SELinux packages
  ```shell
  sudo yum install -y selinux-policy selinux-policy-targeted
  ```
- Edit SElinux configuration file
  ```shell
  sudo vi /etc/selinux/config
  ```
- Set ```ini SELINUX=disabled```
- Verify the status of the SELinux setting
  ```shell
  grep ^SELINUX= /etc/selinux/config
  ```
