## Task: Create a User with a Non-Interactive Shell on App Server 3
------------------------------------------------
step 01: 
Connect App Server 3 
```bash
ssh banner@stapp03
```

Step 02: 
Create the user with a non-interactive shell
```bash
sudo useradd -s /sbin/nologin javed
```

Step 03: 
verify the user
```bash
grep javed /etc/passwd
```



