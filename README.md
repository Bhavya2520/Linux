# Linux

# Quick Reference Commands

## User Management

```bash
sudo adduser username            # Create user
sudo usermod -aG group user     # Add user to group
sudo deluser username           # Delete user
chmod 755 file                  # Change permissions
sudo chown user:group file      # Change ownership

ssh-keygen -t ed25519           # Generate key pair
ssh-copy-id user@server         # Copy public key
ssh -i keyfile user@server      # Connect with specific key

crontab -e                      # Edit crontab
crontab -l                      # List cron jobs
*/15 * * * * command            # Run every 15 minutes
0 2 * * * command               # Run daily at 2 AM

