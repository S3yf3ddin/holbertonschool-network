# 🔧 Networking Basics #1

> Hands-on Bash scripting for Linux network configuration — modifying host-name resolution entries, listing active IP addresses, and opening a listening TCP port.

---

## 🎯 Learning Objectives

By the end of this project you should be able to explain, **without using Google**:

- What the `/etc/hosts` file is and how it controls hostname-to-IP resolution
- How to display all active IPv4 addresses assigned to a machine
- What `localhost` and `127.0.0.1` mean, and the loopback interface
- How to listen on a specific port using `netcat` (`nc`)
- How to test a listening port by connecting to it from another terminal

---

## 📋 Requirements

- Allowed editors: `vi`, `vim`, `emacs`
- Scripts interpreted on **Ubuntu 20.04 LTS**
- All Bash scripts must be executable (`chmod +x`)
- All Bash scripts must pass `shellcheck` without errors
- First line of every Bash script: `#!/usr/bin/env bash`
- Second line of every Bash script: a comment explaining what the script does
- Script `0-change_your_home_IP` **must be run as root** (`sudo`)

---

## 📁 Files

| File | Description |
|------|-------------|
| `0-change_your_home_IP` | Reconfigures `/etc/hosts` — maps `localhost` → `127.0.0.2` and `facebook.com` → `8.8.8.8` |
| `1-show_attached_IPs` | Displays all active IPv4 addresses currently assigned to the machine |
| `2-port_listening_on_localhost` | Opens a listening TCP socket on **port 98** of `localhost` |

---

## ▶️ Usage

### `0-change_your_home_IP` — Update `/etc/hosts`

> ⚠️ **Requires root privileges.** A backup of the original file is saved to `/etc/hosts.bak` before any changes.

```bash
sudo ./0-change_your_home_IP
```

**What it does:**
- Removes any existing entries for `localhost` and `facebook.com`
- Adds `127.0.0.2 localhost`
- Adds `8.8.8.8 facebook.com`

**Verify the change:**
```bash
ping -c 1 localhost    # should reach 127.0.0.2
ping -c 1 facebook.com # should reach 8.8.8.8
```

**Restore the original:**
```bash
sudo cp /etc/hosts.bak /etc/hosts
```

---

### `1-show_attached_IPs` — Display active IPv4 addresses

```bash
./1-show_attached_IPs
```

**Example output:**
```
10.0.2.15
127.0.0.1
```

---

### `2-port_listening_on_localhost` — Listen on port 98

Open **two terminals**:

**Terminal 1 — start the listener:**
```bash
sudo ./2-port_listening_on_localhost
```

**Terminal 2 — connect and send data:**
```bash
telnet localhost 98
# or
nc localhost 98
```

Any text typed in Terminal 2 appears in Terminal 1. Press `Ctrl+C` to stop.

---

## 📖 Background Concepts

### `/etc/hosts`

`/etc/hosts` is a plain-text file that maps hostnames to IP addresses **before** DNS is consulted. It is checked first by the OS resolver.

```
# Format:
<IP address>   <hostname>   [aliases...]

127.0.0.1      localhost
```

### Loopback interface

- `127.0.0.1` is the standard loopback address — traffic sent here never leaves the machine.
- `127.0.0.2` is another valid loopback address (the entire `127.0.0.0/8` block is reserved for loopback).

### `netcat` (`nc`)

`nc` (netcat) is the "Swiss army knife" of networking — it can open TCP/UDP connections, listen on ports, transfer data, and more.

```bash
# Listen on a port
nc -l localhost 98

# Connect to a listening port
nc localhost 98
```

---

## ✍️ Author

**S3yf3ddin** — [GitHub](https://github.com/S3yf3ddin)
