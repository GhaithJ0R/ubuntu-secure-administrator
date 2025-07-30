
## SSH Service Hardening (`/etc/ssh/sshd_config`)

# Change Default SSH Port (e.g. 6767)
Edit the file:
sudo nano /etc/ssh/sshd_config

Set a custom port:

Port 6767

> Remove or comment out any `Port 22` lines.

 Disable Root Login

PermitRootLogin no


Allow Only Specific Users (Optional)

AllowUsers adminuser1 adminuser2


Disable Password Login (Enforce SSH Keys)

PasswordAuthentication no
PubkeyAuthentication yes


Limit Authentication Attempts

MaxAuthTries 3
LoginGraceTime 30


Enable Strict Host Key Checking (Client-side)
Add to `~/.ssh/config`:

Host 
    StrictHostKeyChecking yes
    UserKnownHostsFile ~/.ssh/known_hosts
 Restart SSH Service 
sudo systemctl restart ssh
