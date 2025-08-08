# Crontab Examples

## Time-based Examples

```bash
# Every minute
* * * * * /path/to/script.sh

# Every hour at minute 30
30 * * * * /path/to/script.sh

# Every day at 2:30 AM
30 2 * * * /path/to/script.sh

# Every Monday at 9:00 AM
0 9 * * 1 /path/to/script.sh

# Every 1st day of month at midnight
0 0 1 * * /path/to/script.sh

# Every 15 minutes
*/15 * * * * /path/to/script.sh

# Every weekday at 6:00 AM
0 6 * * 1-5 /path/to/script.sh

# Multiple times per day
0 6,12,18 * * * /path/to/script.sh


Practice Example 
# System backup every day at 2 AM
0 2 * * * /usr/local/bin/backup_script.sh

# Clear temporary files every hour
0 * * * * rm -rf /tmp/temp_*

# Check disk space and send email if low
*/30 * * * * df -h | awk '$5 > 80 {print $0}' | mail -s "Disk Alert" admin@example.com

# Update system package list every week
0 3 * * 0 apt update

# Restart web server every Sunday at 3 AM
0 3 * * 0 systemctl restart apache2



Cron Directories
System-wide Cron Jobs
# View system cron directories
ls -la /etc/cron.d/
ls -la /etc/cron.daily/
ls -la /etc/cron.hourly/
ls -la /etc/cron.monthly/
ls -la /etc/cron.weekly/

# System crontab
cat /etc/crontab

# Add script to run daily
sudo cp script.sh /etc/cron.daily/
sudo chmod +x /etc/cron.daily/script.sh



Environment Variables in Cron
# Set environment variables in crontab
SHELL=/bin/bash
PATH=/usr/local/sbin:/usr/local/bin:/sbin:/bin:/usr/sbin:/usr/bin
MAILTO=admin@example.com

# Use full paths in commands
0 2 * * * /usr/bin/python3 /home/user/script.py

# Source environment before running command
0 2 * * * source /etc/environment && /path/to/script.sh



Cron Logging and Debugging
Check Cron Logs
# View cron logs
sudo tail -f /var/log/cron
sudo tail -f /var/log/syslog | grep cron

# Check if cron is running
sudo systemctl status cron

# Start/stop/restart cron
sudo systemctl start cron
sudo systemctl stop cron
sudo systemctl restart cron



Debugging Cron Jobs
# Test cron job manually
/bin/bash -c "command_from_crontab"

# Add logging to cron job
0 2 * * * /path/to/script.sh >> /var/log/myscript.log 2>&1

# Send output to email
0 2 * * * /path/to/script.sh | mail -s "Script Output" user@example.com

# Redirect all output to file
0 2 * * * /path/to/script.sh > /tmp/output.log 2>&1



Special Cron Strings
# Instead of "0 0 * * *"
@daily /path/to/script.sh

# Other special strings:
@reboot /path/to/startup_script.sh    # Run at startup
@yearly /path/to/annual_script.sh     # Run once a year
@monthly /path/to/monthly_script.sh   # Run once a month
@weekly /path/to/weekly_script.sh     # Run once a week
@hourly /path/to/hourly_script.sh     # Run once an hour

