# Todays Task : Create a Cron Job

**What is cronjob?**
-----------------------------------------------------------------------------------------
A cron job is a scheduled task in Linux/Unix systems that runs automatically at a speciofic time, date or interval. It uses the cron daemon(crond) to execute commands or scripts in the backgroud without human intervention.

For example : 
```bash
0 0 * * * /path/script.sh
```
This means
Minute = 0
Hour = 0 (midnight)
Day = * (every day)
Month = * (every month)
Weekday = * (every day of the week)

So the scripts runs every day at 12.00 am

What is Crond?
-----------------------------------------------------------------------------------------
The daemon/service that actually runs in the background and executes scheduled jobs

commands
```bash
systemctl start crond     
systemctl enable crond    
systemctl status crond    
```

What is crontab?
-----------------------------------------------------------------------------------------
A command-line utility to manage the cron jobs of a user.

Usage:

  crontab -e → edit cron jobs for current user
  
  crontab -l → list cron jobs
  
  crontab -r → remove cron jobs


##  Task.
-----------------------------------------------------------------------------------------
1. Install `cronie` package on all Nautilus app servers.  
2. Start and enable the `crond` service.  
3. Create a cron job for the **root user** that runs every 5 minutes and writes `"hello"` into `/tmp/cron_text`.

Solution: 
-----------------------------------------------------------------------------------------

**Step 01:** SSH into each App Server
```bash
ssh tony@stapp01.stratos.xfusioncorp.com     
ssh steve@stapp02.stratos.xfusioncorp.com    
ssh banner@stapp03.stratos.xfusioncorp.com   
```
**Step 02:** Install Cronie Package
```bash
sudo yum install -y cronie
```
**Step 03:** Start and Enable Crond Service 
```bash
sudo systemctl start crond
sudo systemctl enable crond
sudo systemctl status crond
```
**Step 04:** Add a cronjob for root
```bash
sudo crontab -e
```
add this line 
```bash
*/5 * * * * echo hello > /tmp/cron_text
```
**Step 05:** Verify Cron job
```bash
sudo crontab -l
```
Check the file after 5 minutes:
```bash
cat /tmp/cron_text
```
