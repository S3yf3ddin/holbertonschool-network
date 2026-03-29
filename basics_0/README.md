# Networking Basics #0

This project introduces core networking concepts through multiple-choice questions and Bash scripts.

## Files

### Answer files (multiple-choice)

| File | Description |
|------|-------------|
| `0-OSI_model` | Answers about the OSI model — what it is and how it is organised |
| `1-types_of_network` | Answers about LAN, WAN, and the Internet |
| `2-MAC_and_IP_address` | Answers about MAC addresses and IP addresses |
| `3-UDP_and_TCP` | Answers about the differences between UDP and TCP |

### Bash scripts

| File | Description |
|------|-------------|
| `4-TCP_and_UDP_ports` | Displays all listening sockets with the PID and name of the program to which each socket belongs (`netstat -lp`) |
| `5-is_the_host_on_the_network` | Pings an IP address passed as an argument exactly 5 times |

## Usage

```bash
# Display listening ports
./4-TCP_and_UDP_ports

# Ping a host 5 times
./5-is_the_host_on_the_network <IP_ADDRESS>
```

