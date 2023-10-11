# Basic Commands
Start metasploit console: `msfconsole` \
You can use many normal linux commands like in a linux terminal: `ls, cat, clear, ...`  \
Help: `help <command>` \
Show command history: `history` \
List modules and alike: `show` use `show -h` to see what can be showed \


## Contexts:
Entering a context: `use <context, e.g. exploit>`
Show options: `show options`

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
