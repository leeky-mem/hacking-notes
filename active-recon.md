# Browser (Dev-tools and extensions)
The brower developer options reveal a ton of information about a target website.

## Extenstions
- FoxyProxy - lets you quickly change proxy-servers
- User-Agent Switcher and Manager - lets you change your user Agnets to pretend beeing a different browser or device
- Wappalyzer - shows technologies used on a particular website. Like: analytics, OS, Databases and so on.

# Traceroute
Used to determine how many hops you are away from the target 
`traceroute TARGET_IP`

# Telnet
Telnet is a programm which uses a protocol with the same name. Very old and mostly replaced by ssh.
It can be used though to connect to tcp ports and extract information like: banner, server versions etc.

## Usage
`telnet TARGET_IP PORT` \

when prompted use `GET` requests to extract information. Like `GET / HTTP/1.1`

# Netcat
nc supports both TCP and UDP and can act as a clients and server.
It is a very versatlie tool and here are only the basics covered.

## Usage
`nc TARTGET_IP PORT` \
