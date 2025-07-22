# MariaDB Troubleshooting

## Requirements
There is a critical issue going on with the Nautilus application in Stratos DC. The production support team identified that the application is unable to connect to the database. \
After digging into the issue, the team found that mariadb service is down on the database server.

Look into the issue and fix the same.

## Steps
- SSH into the database server
- Check the status of the database
  ```console
  sudo systemctl status mariadb
  ```
- Try to start the service
  ```console
  sudo systemctl status mariadb
  ```
- The service is in inactive mode. Open the journal logs to see why
    ```console
  sudo journalctl -xeu mariadb.service
  ```
- There is a script that is failing to execute, thereby affecting the startup of the database service
- Upon inspecting the script, it's missing the variables referenced inside the script
- To fix it, add the variables below to the top part of the script
  ```ini
  datadir="/var/lib/mysql"
  errlogfile="/var/log/mariadb/mariadb.log"
  ```
- Create the mysql folder and make sure it's owned by mysql user
  ```console
  sudo mkdir -p /var/lib/mysql
  sudo chown -R mysql:mysql /var/lib/mysql
  ```
- Try starting the service again
  ```console
  sudo systemctl start mariadb
  ```
- It starts, and the service works fine now.
