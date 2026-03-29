# Networking Basics #1

This project covers practical networking tasks on a Linux host using Bash scripts.

## Files

| File | Description |
|------|-------------|
| `0-change_your_home_IP` | Configures `/etc/hosts` so that `localhost` resolves to `127.0.0.2` and `facebook.com` resolves to `8.8.8.8` |
| `1-show_attached_IPs` | Displays all active IPv4 addresses on the machine |
| `2-port_listening_on_localhost` | Listens on TCP port 98 on `localhost` using `nc` |

## Usage

```bash
# Change localhost and facebook.com IP entries (requires root)
sudo ./0-change_your_home_IP

# Show all active IPv4 addresses
./1-show_attached_IPs

# Listen on port 98 (open in one terminal, connect from another)
./2-port_listening_on_localhost
```
 
