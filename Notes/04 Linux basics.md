# Linux Basics

## Linux

- An operating system based on the **Linux kernel**

### Common Linux Distributions

- Ubuntu
- CentOS
- Kali Linux
- Debian
- Arch Linux
- Linux Mint

### Linux Kernel

- Can be modified and distributed
- Can be customized for specific needs

### Kali Linux

- Focused on penetration testing and security

---

# Linux File Structure

| Directory | Purpose |
| --------- | ------- |
| `/` | Root directory |
| `/home` | Home directory for users |
| `/etc` | Configuration files |
| `/var/log` | System log files |
| `/bin` | Essential user binaries |
| `/sbin` | System binaries |
| `/tmp` | Temporary files |

---

# Basic Linux Commands

| Command | Purpose |
| ------- | ------- |
| `pwd` | Print current working directory |
| `cd` | Change directory |
| `ls` | List files/directories |
| `touch` | Create an empty file |
| `mkdir` | Create a directory |
| `mkdir -p` | Create parent and child directories as needed |
| `cat` | Display file contents |
| `tac` | Display file contents in reverse order |
| `gedit` | GUI text editor |
| `nano` | Terminal text editor |
| `vim` | Terminal text editor |
| `head` | Show beginning of a file |
| `tail` | Show end of a file |
| `rmdir` | Remove an empty directory |
| `rm` | Remove files/directories |
| `mv` | Move or rename files |
| `man` | Display manual pages |
| `file` | Identify file type |
| `ping` | Test network connectivity |
| `ip a` | Display IP address information |
| `ifconfig` | Display network interface information (legacy) |

---

# User Management

| Command | Purpose |
| ------- | ------- |
| `adduser` | Interactive user creation |
| `useradd` | Create a user (non-interactive) |
| `passwd` | Set/change a user's password |
| `su` | Switch user |
| `sudo` | Execute commands as another user (typically root) |
| `id` | Display user and group IDs |
| `userdel` | Delete a user |
| `usermod` | Modify a user |
| `chsh` | Change user's login shell |
| `chage` | Manage password aging |
| `groupadd` | Create a group |
| `groupdel` | Delete a group |
| `groups` | Show a user's groups |

### `useradd` vs `adduser`

| `useradd` | `adduser` |
| ---------- | --------- |
| Low-level command | User-friendly wrapper |
| Non-interactive | Interactive |
| Does not prompt for password by default | Prompts for password and user information |

---

# User IDs (UID)

| UID Range | Purpose |
| ---------- | ------- |
| `0` | Root user |
| `1-99` | Predefined users |
| `100-999` | System users |
| `1000+` | Local users |

---

# File Permissions

## Permission Types

- Read (`r`)
- Write (`w`)
- Execute (`x`)

### Ownership

Permissions are assigned to:

- User (Owner)
- Group
- Others

### Permission Format

Example:

```text
-rwxr-xr--
```

- 1st character → File type
- Next 3 → User permissions
- Next 3 → Group permissions
- Last 3 → Others permissions

### Numeric (Octal) Permissions

| Permission | Value |
| ---------- | ----- |
| `r` | 4 |
| `w` | 2 |
| `x` | 1 |
| `-` | 0 |

Permission values are added together.

Examples:

| Symbolic | Numeric |
| -------- | ------- |
| `rwx` | 7 |
| `rw-` | 6 |
| `r-x` | 5 |
| `r--` | 4 |
| `-wx` | 3 |
| `-w-` | 2 |
| `--x` | 1 |
| `---` | 0 |

Example:

```text
rwxr-xr--
```

```
User   Group  Others
rwx    r-x    r--
 7      5      4
```

Equivalent:

```bash
chmod 754 file.txt
```

### Common Permission Examples ( important from cybersecurity / SOC standpoint )

| Permission | Typical Use |
| ---------- | ----------- |
| `777` | Everyone has full access. Rarely appropriate; investigate if found on sensitive files/directories. |
| `755` | Common for executable files and directories. Owner can modify; others can read and execute. |
| `644` | Common for configuration and text files. Owner can modify; others can only read. |
| `600` | Used for sensitive files (SSH keys, credentials). Only the owner has read/write access. |
| `400` | Read-only for the owner. Often used to protect private keys and other critical files. |

#### Why these five?

777 → Immediate red flag during audits or incident response.
755 → Normal for scripts, binaries, and directories.
644 → The default for many Linux files.
600 → Common for secrets (~/.ssh/id_rsa, credentials, tokens).
400 → Used when a file should never be modified accidentally.


### Command

```bash
chmod
```

---

# Paths

## Absolute Path

- Starts with `/`
- Specifies the complete path from the root directory

## Relative Path

- Starts from the current working directory

---

# Process Management

| Command | Purpose |
| ------- | ------- |
| `ps` | Display running processes |
| `ps aux` | Detailed process listing |
| `top` | Real-time process monitor |
| `kill` | Terminate a process using its PID |
| `killall` | Kill processes by name |
| `pkill` | Kill processes matching a pattern |
| `kill -l` | List available kill signals |
| `pidof` | Get the PID of a process |
| `pgrep` | Search for process IDs |
| `systemctl` | Manage systemd services |

### Common `systemctl` Commands

```bash
systemctl start
systemctl stop
systemctl enable
systemctl disable
systemctl status
```

---

# Important Directories for SOC Analysts

| Path | Purpose |
| ---- | ------- |
| `/var/log/auth.log` | Authentication events |
| `/var/log/syslog` | System messages |
| `/var/log/apache2/access.log` | Apache web server access logs |

### Systemd Logs

```bash
journalctl
```

---

# Linux Filters & Utilities

| Command | Purpose |
| ------- | ------- |
| `tee` | Save output to a file while displaying it |
| `grep` | Search for matching text |
| `cut` | Extract columns/fields |
| `wc` | Count lines, words, and characters |
| `sort` | Sort data |
| `uniq` | Remove duplicate adjacent lines |
| `comm` | Compare two sorted files |
| `find` | Search for files/directories |
| `locate` | Find files using a database index |
| `date` | Display date and time |
| `cal` | Display a calendar |
| `tar` | Archive/extract files |
| `whoami` | Show current username |
| `who` | Show logged-in users |

### Common `tar` Commands

```bash
tar -cvf
```

Create an archive.

```bash
tar -xvf
```

Extract an archive.

---

## `su`

```bash
su username
```

- Switch to another user.
- Requires the target user's password.

## `sudo su` vs `su root`

- TODO: Understand the difference.

## Shadow File

- TODO: Learn about `/etc/shadow`.

## Topics to Explore

- [ ] Medusa
- [ ] Seppuku
- [ ] `sudo su` vs `su root`
- [ ] `/etc/shadow`

---
