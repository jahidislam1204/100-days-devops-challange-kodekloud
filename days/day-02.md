### Task: Create a Temporary User with Expiry on App Server 2

Step 01: Connect to App Server 2
```bash
ssh steve@stapp02
```

Step 02: Create the user john with expiry date - 2023-12-07
```bash
sudo useradd -e 2023-12-07 john
```

Step 03: Verify the User and Expiry date 

Check the user
```bash
grep john /etc/passwd
```
Check the expiry details
```bash
grep john /etc/passwd
```
