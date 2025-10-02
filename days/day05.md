# Day 05 – SELinux Installation & Configuration 

Today’s challenge in the **100 Days of DevOps (KodeKloud)** journey was focused on **SELinux** (Security-Enhanced Linux), which is a mandatory access control system built into Linux. It provides an additional layer of security by restricting processes, files, and users.

---

##  Task  
On **App Server 1** (`stapp01.stratos.xfusioncorp.com`), the requirements were:

1. Install the required SELinux packages.  
2. Permanently disable SELinux for now (it will be re-enabled after further configuration).  
3. No need to reboot immediately — a scheduled maintenance reboot is already planned.  

---

## 🛠️ Steps I Followed  

### 1. SSH into App Server 1
```bash
ssh tony@stapp01.stratos.xfusioncorp.com
```
### 2. Install SELinux Packages
```bash
sudo yum install -y policycoreutils selinux-policy selinux-policy-targeted
```
### 3. Permanently Disable SELinux
   
Edited the SELinux config file:
```bash
sudo vi /etc/selinux/config
```
Changed the line:
```bash
SELINUX=enforcing
```
to:
```bash
SELINUX=disabled
```
### 4. Verified Configuration
```bash
grep ^SELINUX= /etc/selinux/config
```
