### File Permissions & Executable Scripts

SSH into Jump Host
```bash
ssh thor@jump_host.stratos.xfusioncorp.com
```
Connect to the app server02
```bash
ssh steve@stapp02.stratos.xfusioncorp.com
```

check the permission of /tmp/xfusioncorp.sh
```bash
ls -l /tmp/xfusioncorp.sh
```

Change the permission (Add read permission first and then add execute permission)
```bash
chmod +rx /tmp/xfusioncorp.sh
```
Now check the permission of /tmp/xfusioncorp.sh
```bash
ls -l /tmp/xfusioncorp.sh
```
Test the file execution (without sudo)
```bash
/tmp/xfusioncorp.sh
```
