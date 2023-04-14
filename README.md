# SubSleuth - A Subdomain Enumeration Tool

This script is a subdomain enumeration tool that takes a target domain and a file containing a list of subdomains as input. It then checks if each subdomain exists and finds the specified accessible ports.

## Dependencies

- `dns.resolver`: A DNS resolver library for Python.
- `argparse`: A command-line argument parsing library for Python.
- `socket`: A low-level networking library for Python.
- `tabulate`: A library for creating beautiful ASCII tables in Python.

## Usage

```bash
python subdomain_enum.py <domain> <subdomains_file> [-p <ports>]
```
* domain: The target domain to enumerate subdomains.
* subdomains_file: A file containing a list of subdomains to check against the target domain.
* -p or --ports (optional): A list of ports to check for accessibility (default: 80, 443).

## How it works

1. Read the subdomains from the specified text file.
2. Enumerate subdomains by resolving their IP addresses using the DNS resolver.
3. Check accessible ports for each discovered subdomain using the socket library.
4. Display the results in a tabulated format.

## Example
```bash
python subdomain_enum.py example.com subdomains.txt -p 80 443
```

## Example Output
```bash
python find_subdomains.py google.com subdomains.txt


███████╗██╗   ██╗██████╗ ███████╗██╗     ███████╗██╗   ██╗████████╗██╗  ██
██╔════╝██║   ██║██╔══██╗██╔════╝██║     ██╔════╝██║   ██║╚══██╔══╝██║  ██
███████╗██║   ██║██████╔╝███████╗██║     █████╗  ██║   ██║   ██║   ███████
╚════██║██║   ██║██╔══██╗╚════██║██║     ██╔══╝  ██║   ██║   ██║   ██╔══██
███████║╚██████╔╝██████╔╝███████║███████╗███████╗╚██████╔╝   ██║   ██║  ██║
╚══════╝ ╚═════╝ ╚═════╝ ╚══════╝╚══════╝╚══════╝ ╚═════╝    ╚═╝   ╚═╝  ╚═╝

Subdomain             IP Address       Accessible Ports
--------------------  ---------------  ------------------
www.google.com        142.250.217.68   [80, 443]
mail.google.com       142.250.69.197   [80, 443]
drive.google.com      172.217.14.238   [80, 443]
docs.google.com       172.217.14.238   [80, 443]
classroom.google.com  142.251.211.238  [80, 443]
```
