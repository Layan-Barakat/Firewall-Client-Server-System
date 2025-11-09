# Firewall Client-Server System

This project implements a **client–server architecture in C** that manages a set of firewall rules and handles network requests interactively or remotely. The system validates IP and port ranges, maintains command history, and supports rule addition, connection checks, deletion, and listing.

---

## ⚙️ Features
- Add, delete, and list firewall rules (`A`, `D`, `L` commands)
- Check incoming connections (`C` command)
- View command history (`R` command)
- Interactive mode (`-i` flag) or network mode
- Thread-safe handling of requests using `pthread` mutexes
- Validation of IP ranges, port ranges, and formats

---

## Files
| File | Description |
|-------|-------------|
| `annotated-server.c.pdf` | Server program with interactive and network modes |
| `annotated-client.c.pdf` | Client program that connects to the server and sends commands |

---

## How to Compile and Run
```bash
# Compile both files
gcc annotated-server.c -o server -lpthread
gcc annotated-client.c -o client

# Start the server on a port (e.g., 8080)
./server 8080

# OR run in interactive mode
./server -i

# Connect with the client
./client 127.0.0.1 8080 A 192.168.0.1 80-90
