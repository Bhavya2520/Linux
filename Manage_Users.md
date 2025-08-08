# Linux User, Group, Permissions & SSH Reference

---

## Creating Users

```bash
# Create a new user
sudo adduser username

# Alternative command (more basic)
sudo useradd username

# Create user with specific home directory
sudo useradd -m -d /home/custompath username

# Create user with specific shell
sudo useradd -s /bin/bash username


## Modifying Users
# Change user password
sudo passwd username

# Change user's login shell
sudo usermod -s /bin/zsh username

# Add user to a group
sudo usermod -aG groupname username

# Change user's home directory
sudo usermod -d /new/home/path username

# Lock a user account
sudo usermod -L username

# Unlock a user account
sudo usermod -U username


## Deleting Users
# Delete user but keep home directory
sudo deluser username

# Delete user and home directory
sudo deluser --remove-home username

# Alternative command
sudo userdel -r username


## Group Management
# Create a new group
sudo addgroup groupname
# or
sudo groupadd groupname

# Delete a group
sudo delgroup groupname
# or
sudo groupdel groupname

# View all groups
cat /etc/group

# View groups for specific user
groups username

# View current user's groups
groups


## File Permissions and Ownership
# View file permissions
ls -l filename
ls -la directory/

# Permission format: drwxrwxrwx
# d = directory (- for files)
# rwx = owner permissions (read, write, execute)
# rwx = group permissions
# rwx = other users permissions


## Changing Permissions (chmod)
# Using numeric notation
chmod 755 filename    # rwxr-xr-x
chmod 644 filename    # rw-r--r--
chmod 600 filename    # rw-------

# Using symbolic notation
chmod u+x filename    # Add execute for owner
chmod g-w filename    # Remove write for group
chmod o+r filename    # Add read for others
chmod a+x filename    # Add execute for all

# Recursive permission change
chmod -R 755 directory/


## Changing Ownership (chown)
# Change owner
sudo chown newowner filename

# Change owner and group
sudo chown newowner:newgroup filename

# Change only group
sudo chown :newgroup filename
# or
sudo chgrp newgroup filename

# Recursive ownership change
sudo chown -R owner:group directory/


## Special Permissions
# Set sticky bit (only owner can delete files in directory)
chmod +t directory/
chmod 1755 directory/

# Set SUID (run with owner's permissions)
chmod +s filename
chmod 4755 filename

# Set SGID (inherit group ownership)
chmod g+s directory/
chmod 2755 directory/


## Access Control Lists (ACLs)
# View ACLs
getfacl filename

# Set ACL permissions
sudo setfacl -m u:username:rwx filename  # User permissions
sudo setfacl -m g:groupname:rx filename  # Group permissions
sudo setfacl -m o:r filename             # Others permissions

# Remove ACL
sudo setfacl -x u:username filename

# Remove all ACLs
sudo setfacl -b filename


## SSH Key-Based Authentication on Ubuntu
Generating SSH Keys
bash
Copy
Edit
# Generate RSA key pair (default)
ssh-keygen -t rsa -b 4096 -C "your_email@example.com"

# Generate ED25519 key pair (recommended)
ssh-keygen -t ed25519 -C "your_email@example.com"

# Specify custom filename
ssh-keygen -t ed25519 -f ~/.ssh/custom_key -C "your_email@example.com"
SSH Connection Commands
bash
Copy
Edit
# Connect using default key
ssh username@server_ip

# Connect using specific key
ssh -i ~/.ssh/custom_key username@server_ip

# Connect with port specification
ssh -p 2222 username@server_ip

# SSH with X11 forwarding
ssh -X username@server_ip

# SSH with port forwarding
ssh -L 8080:localhost:80 username@server_ip
