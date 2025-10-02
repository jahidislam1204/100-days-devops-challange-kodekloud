## disable direct SSH root login

**Login to the jump host**
```bash
ssh thor@jump_host.stratos.xfusioncorp.com
```
**For stapp01 **

login stapp01
 ```bash
ssh tony@stapp01.stratos.xfusioncorp.com
```
Back up sshd_config
```bash
sudo cp /etc/ssh/sshd_config /etc/ssh/sshd_config.bak.$(date +%F)
```
set the rule
```bash
sudo sed -i 's/^[#[:space:]]*PermitRootLogin\s\+.*/PermitRootLogin no/' /etc/ssh/sshd_config
```

If it didn’t exist at all, append it
```bash
grep -qi '^PermitRootLogin' /etc/ssh/sshd_config || echo 'PermitRootLogin no' | sudo tee -a /etc/ssh/sshd_config
```
Validate config syntax
```bash
sudo sshd -t
```
Reload
```bash
sudo systemctl reload sshd
```
Exit from the stapp01
```bash
exit
```

**For stapp02 **

login stapp02
 ```bash
ssh steve@stapp02.stratos.xfusioncorp.com
```
Back up sshd_config
```bash
sudo cp /etc/ssh/sshd_config /etc/ssh/sshd_config.bak.$(date +%F)
```
set the rule
```bash
sudo sed -i 's/^[#[:space:]]*PermitRootLogin\s\+.*/PermitRootLogin no/' /etc/ssh/sshd_config
```

If it didn’t exist at all, append it
```bash
grep -qi '^PermitRootLogin' /etc/ssh/sshd_config || echo 'PermitRootLogin no' | sudo tee -a /etc/ssh/sshd_config
```
Validate config syntax
```bash
sudo sshd -t
```
Reload
```bash
sudo systemctl reload sshd
```
Exit from the stapp02
```bash
exit
```

**For stapp03 **

login stapp03
 ```bash
ssh banner@stapp03.stratos.xfusioncorp.com
```
Back up sshd_config
```bash
sudo cp /etc/ssh/sshd_config /etc/ssh/sshd_config.bak.$(date +%F)
```
set the rule
```bash
sudo sed -i 's/^[#[:space:]]*PermitRootLogin\s\+.*/PermitRootLogin no/' /etc/ssh/sshd_config
```

If it didn’t exist at all, append it
```bash
grep -qi '^PermitRootLogin' /etc/ssh/sshd_config || echo 'PermitRootLogin no' | sudo tee -a /etc/ssh/sshd_config
```
Validate config syntax
```bash
sudo sshd -t
```
Reload
```bash
sudo systemctl reload sshd
```
Exit from the stapp03
```bash
exit
```

Check the root can't login via ssh

```bash
ssh root@stapp01.stratos.xfusioncorp.com
ssh root@stapp02.stratos.xfusioncorp.com
ssh root@stapp03.stratos.xfusioncorp.com
```
