# Samba Setup

1. Edit the Samba configuration:
   `sudo nano /etc/samba/smb.conf`

2. Configure the required storage share.

3. Restrict access using `valid users`.

4. Restart Samba:
   `sudo systemctl restart smbd`

5. Check Samba users:
   `sudo pdbedit -L`

6. Remove unused Samba accounts when required:
   `sudo pdbedit -x -u mrkid`
