# Raspberry Pi NAS & Secure Remote Access

A home Network-Attached Storage (NAS) and secure remote-access project built using a Raspberry Pi 2 Model B v1.1, Samba/SMB, SSH, and Tailscale VPN.

## Project Overview

The main objective was to configure a Raspberry Pi as a network-attached storage server for file sharing across a local network. Tailscale was added to provide secure remote access without directly exposing NAS services through router port forwarding.

## Technologies

- Raspberry Pi 2 Model B v1.1
- Linux / Raspberry Pi OS
- Samba (SMB)
- SSH
- Tailscale VPN
- WireGuard encrypted tunneling
- Windows client

## Architecture

```text
Internet
   |
Tailscale VPN
   |
Encrypted Tunnel
   |
+-----------------------+
| Raspberry Pi NAS      |
| Linux                 |
| Samba / SMB           |
| SSH                   |
| Tailscale             |
+-----------+-----------+
            |
      External HDD
            |
       NAS Storage
            |
      Windows Client
```

## Main Features

- Network file sharing using Samba
- User-based Samba authentication
- Least-privilege access control
- SSH remote administration
- Secure remote access using Tailscale
- Troubleshooting and configuration documentation

## Commands

See `commands/commands.md` for the complete command list used during the project.

## Configuration

See `configs/smb.conf.example` for an example Samba share configuration.

> Do not upload passwords, private keys, authentication tokens, or other secrets.

## Screenshots

Project screenshots can be placed inside:

- `screenshots/raspberry-pi/`
- `screenshots/samba/`
- `screenshots/tailscale/`
- `screenshots/windows/`

## Security Considerations

### Principle of Least Privilege
Only the required Samba user was granted access to the configured share.

### Reduced Attack Surface
Tailscale was used for remote access instead of exposing SMB/SSH services directly to the public internet through router port forwarding.

### Encrypted Communication
SSH and the Tailscale VPN provide encrypted communication for administration and remote access.

## Troubleshooting

### Samba user database
```bash
sudo pdbedit -L
sudo pdbedit -x -u mrkid
```

### Windows SMB cache
```cmd
net use * /delete
```

### SSH host-key mismatch
```cmd
ssh-keygen -R 192.168.1.8
```

## Future Improvements

- Automated NAS backups
- Disk health monitoring
- Storage monitoring
- Automated security updates
- File integrity monitoring
- Web-based file management
- Centralized logging and monitoring

## Author

**Henuka Munasinghe**

Cyber Security & Network Student
