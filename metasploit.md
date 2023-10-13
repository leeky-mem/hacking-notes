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

## Contexts:
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
`check` - Check if target is vulnerable without exploiting. Not supported by all modules. \

## Sessions:
Once a vulnerabilitay has successfully been exploited, a session is started.

`background` - Sends the session to the background and presents the context prompt again \
`CTRL + Z` - Same as Background \
`sessions` - List sessions \
`sessions -i <session-number>` - Interact with the session


# Scanning
There are many many scanners use `search scanner <what_you_need>` \
## UDP
**udp_sweep** \
`run` 

## SMB
**smb_enumshares** \
**smb_version** \

# Database mode
`systemctl start postgresql` \
`msfdb init` \
`mfsconsole` \
`db_status` \

## Workspaces
`workspace -a` - add new workspace \
`workspace -d` - delet \
`-h` - lists options \
`help` - lists the db backend commands \
`db_nmap` - runs nmap but stores results in db \
