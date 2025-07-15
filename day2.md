# Create a linux user javed with expiry date

## Solution
- Execute
```shell
sudo useradd -e 2024-15-04 javed
```
- Check the account expiration with
```shell
sudo chage -l javed
```  
