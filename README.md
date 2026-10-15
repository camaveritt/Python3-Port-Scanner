# Port Scanner

A Python port scanner that checks a range of ports on a target host and reports which ones are open. It accepts either a URL or an IP address.

## Files

- `port_scanner.py`: contains the `get_open_ports()` function
- `common_ports.py`: a dictionary mapping common port numbers to service names (used for verbose output)

## Usage

```python
from port_scanner import get_open_ports

# Returns a list of open ports
get_open_ports("scanme.nmap.org", [20, 80])

# Returns a formatted report with service names
print(get_open_ports("scanme.nmap.org", [20, 80], verbose=True))
```

Example verbose output:

```
Open ports for scanme.nmap.org (45.33.32.156)
PORT     SERVICE
22       ssh
80       http
```

## Parameters

| Parameter | Description |
| --- | --- |
| `target` | A hostname (like `example.com`) or an IP address |
| `port_range` | A list with the first and last port to scan, such as `[20, 80]` |
| `verbose` | If `True`, returns a readable report instead of a list (default `False`) |

Invalid hostnames and IP addresses return an error message instead of a result.

## Note

Only scan hosts you own or have permission to test. [scanme.nmap.org](http://scanme.nmap.org) is a server provided for practice scanning.
