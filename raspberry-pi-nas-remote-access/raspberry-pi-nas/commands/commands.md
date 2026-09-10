# Project Commands

## Linux & Samba

### Edit Samba configuration
```bash
sudo nano /etc/samba/smb.conf
```

### Restart Samba
```bash
sudo systemctl restart smbd
```

### Remove a Samba user
```bash
sudo pdbedit -x -u mrkid
```

### List Samba users
```bash
sudo pdbedit -L
```

### Check Raspberry Pi IP address
```bash
hostname -I
```

### Open Raspberry Pi configuration
```bash
sudo raspi-config
```

## Tailscale

### Install Tailscale
```bash
curl -fsSL https://tailscale.com/install.sh | sh
```

### Connect / authenticate
```bash
sudo tailscale up
```

### Disconnect
```bash
sudo tailscale down
```

### Stop Tailscale service
```bash
sudo systemctl stop tailscaled
```

## Windows

### SSH to Raspberry Pi
```cmd
ssh kid03@192.168.1.8
```

### SSH using Tailscale IP
```cmd
ssh kid03@[Tailscale_IP]
```

### Remove old SSH host key
```cmd
ssh-keygen -R 192.168.1.8
```

### Test connectivity
```cmd
ping 192.168.1.8
```

### Clear Windows SMB sessions
```cmd
net use * /delete
```

### Disconnect Tailscale
```cmd
tailscale down
```
