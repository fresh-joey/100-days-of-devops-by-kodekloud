# Linux Bash Scripts

## Requirements
The production support team of xFusionCorp Industries is working on developing some bash scripts to automate different day to day tasks. One is to create a bash script for taking websites backup. They have a static website running on App Server 3 in Stratos Datacenter, and they need to create a bash script named media_backup.sh which should accomplish the following tasks. (Also remember to place the script under /scripts directory on App Server 3). \
a. Create a zip archive named xfusioncorp_media.zip of /var/www/html/media directory. \
b. Save the archive in /backup/ on App Server 3. This is a temporary storage, as backups from this location will be clean on weekly basis. Therefore, we also need to save this backup archive on Nautilus Backup Server. \
c. Copy the created archive to Nautilus Backup Server server in /backup/ location. \
d. Please make sure script won't ask for password while copying the archive file. Additionally, the respective server user (for example, tony in case of App Server 1) must be able to run it. \


## Steps
- SSH into the server
- Create the media_backup.sh file in the scripts folder and put the details below
  ```ini
  #!/bin/bash
  backup_dir="/backup"
  source_dir="/var/www/html/media"
  file_name="xfusioncorp_media.zip"
  remote_user=clint
  remote_host=172.16.238.16
  remote_dir="/backup"
  
  sudo zip -r "$backup_dir/$file_name" "$source_dir"
  
  scp "$backup_dir/$file_name" $remote_user@$remote_host:$remote_dir/
  ```
- Change permission to execute and owner
  ```console
  sudo chown -R $USER:$USER /scripts
  chmod +x media_backup.sh
  ```
- Generate SSH keys for passwordless copy
  ```console
  ssh-keygen -t rsa -C Appserver3
  ssh-copy-id clint@172.16.238.16
  ```
- Run the script
- SSH into the backup server to verify the file was copied successfully
