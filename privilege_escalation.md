# Enumeration
## Linux
**Commands:** \
`whoami` - gives the current user \
`hostname` - hostname of target machine \
`uname -a` - prints system information like OS and kernel version, hostname, system time, arch ... \
`ps` - show processes, `-a` or `-e` show all processes, `-axjf` shwo process tree \
`env` - show envirinment variables \
`sudo -l` - show what commands can be run as root with sudo \
`id` -shows user privileges and groups 

**Files** \
`/proc/version` - proc file system (procfs) gives more info about the kernel and istalled tool like compilers \
`/etc/issue` - system file, contains info about the OS \
`/etc/passwd` - shows users and other info, in this context we are only interested in the users \
`cat /etc/passwd | cut -d ":" -f 1` - cuts out only the users in passwd, can be used for brute force attacks

**Network** \
`ifconfig` \
`ip toute` \
`netstat` - shows info about existing communications \
>`-a` - shows all listening ports and established comms \
>`-at` / `-au` - lists TCP reso. UDP \
>`-l` - list ports in listening mode \
>`-s` - shows usage statistics by protocol, can be combiled with spesific protocol filters \
>`-p` - shows connections with service name and PID info, can also be combined with specific protocols \
>`-i` - shows interface statistics

**find** \
see [find](https://github.com/leeky-mem/linux-notes/blob/main/commands.md) for basics. For privilege escalation searching for specific permissions is important. \
`-perm mode` - mode can be u,g,o(i.e user,goup,other). In this mode permission bits must match exactly. `-perm o=w` matches onls file which have mode 0020. \
`-perm -mode` - matches all files wich have mode, but not exclusivly \  
`find / -perm -u=s -type f 2>/dev/null` - find files with SUID bit set. SUID bit allows to run the file with the privilege level of the owner. \

# Automated
[LinPeas](https://github.com/carlospolop/privilege-escalation-awesome-scripts-suite/tree/master/linPEAS) - scrip .sh
[LinEnum](https://github.com/rebootuser/LinEnum) - script .sh
[LES (Linux Exploit Suggester)](https://github.com/mzet-/linux-exploit-suggester) - script .sh
[Linux Smart Enumeration](https://github.com/diego-treitos/linux-smart-enumeration) - script .sh
[Linux Priv Checker](https://github.com/linted/linuxprivchecker) - script python or .sh
