# 🖧 Networking Basics #0

> An introduction to core networking theory — the OSI model, network types, addressing, and transport protocols — answered through multiple-choice files, plus practical Bash scripts for port inspection and host reachability.

---

## 🎯 Learning Objectives

By the end of this project you should be able to explain, **without using Google**:

- What the OSI model is and how it is organised (layers and their roles)
- The difference between a LAN, a WAN, and the Internet
- What a MAC address is and what an IP address is
- The difference between TCP and UDP, and when each is used
- What a port is, and what the common port numbers are (SSH → 22, HTTP → 80, HTTPS → 443)
- How to use `netstat` to display listening ports
- What ICMP is and how to use `ping` to check host reachability

---

## 📋 Requirements

- Allowed editors: `vi`, `vim`, `emacs`
- Scripts interpreted on **Ubuntu 20.04 LTS**
- All Bash scripts must be executable (`chmod +x`)
- All Bash scripts must pass `shellcheck` without errors
- First line of every Bash script: `#!/usr/bin/env bash`
- Second line of every Bash script: a comment explaining what the script does

---

## 📁 Files

### 🗂️ Answer files (multiple-choice)

Each file contains the number(s) of the correct answer(s) to the corresponding question set.

| File | Question topic | Answer(s) |
|------|---------------|-----------|
| `0-OSI_model` | What is the OSI model and how is it organised? | `2`, `2` |
| `1-types_of_network` | LAN vs WAN vs Internet | `3`, `2`, `1` |
| `2-MAC_and_IP_address` | MAC address vs IP address | `2`, `1` |
| `3-UDP_and_TCP` | TCP vs UDP characteristics | `1`, `2`, `1` |

### 🔧 Bash scripts

| File | Description |
|------|-------------|
| `4-TCP_and_UDP_ports` | Displays all listening sockets along with the PID and program name attached to each socket |
| `5-is_the_host_on_the_network` | Accepts an IP address as an argument and pings it exactly **5 times** |

---

## ▶️ Usage

### `4-TCP_and_UDP_ports` — List listening ports

```bash
sudo ./4-TCP_and_UDP_ports
```

**Example output:**
```
Active Internet connections (only servers)
Proto Recv-Q Send-Q Local Address   Foreign Address  State    PID/Program name
tcp        0      0 0.0.0.0:22      0.0.0.0:*        LISTEN   1234/sshd
tcp6       0      0 :::80           :::*             LISTEN   5678/apache2
```

---

### `5-is_the_host_on_the_network` — Ping a host 5 times

```bash
./5-is_the_host_on_the_network <IP_ADDRESS>

# Example:
./5-is_the_host_on_the_network 8.8.8.8
```

**Example output:**
```
PING 8.8.8.8 (8.8.8.8) 56(84) bytes of data.
64 bytes from 8.8.8.8: icmp_seq=1 ttl=63 time=10.1 ms
...
--- 8.8.8.8 ping statistics ---
5 packets transmitted, 5 received, 0% packet loss
```

---

## 📖 Background Concepts

### OSI Model (7 layers)

| Layer | Name | Example protocols |
|-------|------|-------------------|
| 7 | Application | HTTP, FTP, SSH |
| 6 | Presentation | SSL/TLS |
| 5 | Session | NetBIOS |
| 4 | Transport | TCP, UDP |
| 3 | Network | IP, ICMP |
| 2 | Data Link | Ethernet, MAC |
| 1 | Physical | Cables, Wi-Fi signals |

### TCP vs UDP

| Feature | TCP | UDP |
|---------|-----|-----|
| Connection | Connection-oriented | Connectionless |
| Reliability | Guaranteed delivery | Best-effort |
| Order | In-order delivery | No ordering |
| Speed | Slower (overhead) | Faster |
| Use cases | HTTP, SSH, FTP | DNS, video streaming, VoIP |

---

## ✍️ Author

**S3yf3ddin** — [GitHub](https://github.com/S3yf3ddin)

