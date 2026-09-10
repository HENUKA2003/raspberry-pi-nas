# Architecture

The Raspberry Pi acts as the NAS server and stores files on an external hard drive.

Samba provides authenticated SMB file sharing to Windows clients on the local network.

Tailscale provides encrypted remote connectivity, allowing administration and file access without directly exposing NAS services to the public internet.

```text
Local Network:
Windows PC ---- SMB ---- Raspberry Pi NAS ---- External HDD

Remote Access:
Windows PC ---- Tailscale/WireGuard ---- Raspberry Pi NAS
```
