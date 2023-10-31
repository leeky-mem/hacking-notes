# Passive reconnaissance

## WHOIS
`whois` is a domain lookup tool.
It reveils usfull information about the domain and the domain registrar

### Usage
`whois DOMAIN` example `whois tryhackme.com`

## nslookup
Name Server Look Up: Used to look up Ip addresses, mail servers, text record and alike from a specific domain.

### Usage
`nslookup OPTIONS DOMAIN` example `nslookup -type=a tryhackme.com` to get type A records for the tryhackme.comm domain.

Options (`-type=`):
- A 	-> IPv4 Addresses
- AAAA 	-> IPv6 Addresses
- CNAME -> canonical name
- MX 	-> Mail Servers
- SOA 	-> Sart of Authority
- TXT 	-> Text records

## dig
dig is similar to nslookup. SOmetime displays more info

### Usage
`dig DOMAIN OPTIONS` example: `dig tryhackme MX` to get the mailsercers of the tryhackme domain.

Options: same as nslookup

## DNSDumpster (Webtool)
dnsdumpster.com

### Usage
Enter the domain to be inspected in the search field
