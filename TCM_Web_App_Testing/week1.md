# Week 1

## Resources

- [Github](github.com/hmaverickadams)
- Juice Shop for Learning
- OWASP Test Guide
- Portswigger web security academy
- Look ay writeups

## Steps of Hacking

1. Recon
   - Active
   - Passive
2. Scanning and Enumeration
3. Gaining Access
4. Maintaining Access
5. Covering Tracks

# Recon

- Target Validation
  - WHOIS, nslookup, dnsrecon
- Finding Subdomains
  - Google Fu, dig, nmap, sublist3r, bluto, crt.sh
- Finger Printing
  - nmap, wappalyzer, WhatWeb, BuiltWith, Netcat
- Data Breaches
  - HaveIBeenPwned and similar lists

## Tools

### Sublister

- To install use `sudo apt get install sublist3r`
- To run against a domain use `sublist3r -d <domain name>`

### crt.sh

- [crt.sh](crt.sh) is a website that can be used to find information about subdomains
- % can be used as as wildcard, example `%.google.com` for all google subdomains

### Burpsuite

- can be installed by `sudo apt get install burpsuite`

### Websites

- [securityheaders.io](securityheaders.io)
- Wapalyzer
- [builtwith.com](builtwith.com)
- [hunter.io](hunter.io)

### Nikto

- usage `nikto -h https://<url>`

### nmap

- ssl-enum-cipers
