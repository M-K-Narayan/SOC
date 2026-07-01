# Windows Architecture & SOC Essentials

## Architecture

### User Mode vs Kernel Mode

| User Mode | Kernel Mode |
| ---------- | ----------- |
| All user applications run here. | Has unrestricted access to system memory and hardware. |
| Uses system calls to request OS services. | Handles memory management, process scheduling, and hardware interaction. |

## Key Components (Important for SOC Analysts)

- **HAL (Hardware Abstraction Layer)** - Bridges the OS and hardware (implemented primarily through hal.dll)
- **NTOSKRNL.exe (Windows Kernel)** - Manages core OS operations (ntoskrnl.exe is the kernel image)
- **System services and drivers** - Run in kernel mode and communicate with hardware/devices.
- **Win32 Subsystem** - Manages GUI and console applications.

## Essential Processes to Look for in Task Manager

- **System** - Manages hardware-related operations.
- **wininit.exe** - Starts essential Windows services after boot.
- **csrss.exe** - Client Server Runtime Process.
- **svchost.exe** - Generic host process for Windows services. Multiple instances are normal.

---

# Important Windows Directories

## `C:\Windows\System32`

- OS-level executables and libraries.
- Common target for persistent malware.

## `C:\Users\`

- Home directory for users (similar to `/home` in Linux).
- Each user has folders like:
  - Desktop
  - Documents
  - Downloads
- Common location where malware may be dropped for execution.

### Persistent vs Non-Persistent Attacks

- **Persistent malware** often focuses on locations like `System32` or persistence mechanisms.
- **Non-persistent malware** usually does not survive a reboot.

## `C:\Program Files` / `C:\Program Files (x86)`

- Installed application directories.

## `%APPDATA%` and `%LOCALAPPDATA%`

- Hidden folders storing user-specific application data.
- Common malware location:
  - `C:\Users\<username>\AppData\Roaming\`

---

# Task Manager

**Shortcut**

```text
Ctrl + Shift + Esc
```

Useful tabs:

- Processes
- Performance
- Startup
- Users

Uses:

- View running processes.
- Identify suspicious or rogue processes.
- Monitor system resource usage.

---

# Important Windows Commands

Press **Win + R**, then enter:

## `msconfig`

System Configuration

- Startup configuration
- Boot configuration
- Startup apps and services

## `eventvwr`

Event Viewer

- View Windows logs.
- Event IDs are very important.
- Shows system, application, and security events.

## `regedit`

Registry Editor

- View and modify system/user configuration.

## `services.msc`

Services Manager

- View installed Windows services.
- Start, stop, or configure services.

---

# Windows Event Logs (SOC Perspective)

Path:

```text
Event Viewer
└── Windows Logs
    ├── Application
    ├── Security
    └── System
```

## Log Types

- **Application** - Logs from installed programs.
- **System** - OS events such as driver failures and startup issues.
- **Security** - Authentication, login events, and access control.

## Important Event IDs

| Event | ID |
| ------ | --: |
| Successful login | 4624 |
| Failed login | 4625 |
| Logoff | 4634 |
| Process created | 4688 |
| Special privileges assigned | 4672 |
| Security logs cleared (red flag) | 1102 |
| User account created | 4720 |
| User account deleted | 4726 |
| New service installed | 4697 |

> Event IDs are very important for SOC analysis.
>
> Event IDs can vary depending on the Windows version and log source.

---

# Windows CLI Basics

- `ipconfig`
  - Shows IP address and network interface information.

- `netstat`
  - Shows open ports and active connections.

```powershell
netstat -ano
```

- Shows active connections.
- Listening ports.
- Numerical addresses.
- Associated PID.

- ```
- tasklist
- ```
  - Lists running processes.

- `taskkill /PID <PID> /F`
  - Forcefully terminates a process by PID.

- `whoami`
  - Shows the currently logged-in user.

- `systeminfo`
  - Displays OS version, patch level, uptime, and system information.

- `wmic process list brief`
  - Lists running processes using WMIC (legacy Windows utility).

- `powershell`
  - Provides powerful scripting and automation capabilities beyond Command Prompt.

> There are many more Windows commands worth learning.

---

# Common Persistence Techniques

## Startup Folder

```text
C:\Users\<user>\AppData\Roaming\Microsoft\Windows\Start Menu\Programs\Startup
```

- `.exe` and `.bat` files placed here execute when the user logs in.

## Registry Run Keys

```text
HKCU\Software\Microsoft\Windows\CurrentVersion\Run
```

- Attackers can place commands here for automatic execution at login.

## Scheduled Tasks

- Created using:

```powershell
schtasks
```

- Can be used to create recurring or hidden tasks.

## Malicious Services

- Attackers may create fake services using:

```powershell
sc.exe
```

- Used to hide or maintain malicious programs.

---

# Useful Windows Tools for SOC Analysts

- Sysinternals Suite
  - Process Explorer
  - Autoruns
  - TCPView
- Windows Defender logs
- Reliability Monitor
- Process Hacker - is now known as System Informer (though many people still refer to it by its old name).

---
