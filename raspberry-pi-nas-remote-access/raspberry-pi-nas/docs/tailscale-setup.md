# Tailscale Setup

Tailscale was used to provide secure remote access to the Raspberry Pi.

Install:
```bash
curl -fsSL https://tailscale.com/install.sh | sh
```

Connect:
```bash
sudo tailscale up
```

Disconnect:
```bash
sudo tailscale down
```

Stop the Linux service:
```bash
sudo systemctl stop tailscaled
```

Remote SSH can then use the Raspberry Pi's Tailscale IP:
```bash
ssh kid03@[Tailscale_IP]
```
