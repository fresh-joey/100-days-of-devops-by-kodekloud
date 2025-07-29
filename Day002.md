# Temporary User Setup with Expiry

## Requirements
- Create a user account named javed that is set to expire on 2024-15-04

## Steps
- SSH into the server
- Add user `javed` and set expiry date for the account
```console
sudo useradd -e 2024-15-04 javed
```
- Check the account expiration with
```console
sudo chage -l javed
```  
