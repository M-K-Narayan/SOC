# Linux Logs

Many enterprises today use Linux on their servers.

Hence, knowing Linux inside out is very important.

It helps in:

- Troubleshooting
- Intrusion Detection
- Security Monitoring

Logs track almost everything, such as:

- Boot process
- User logins
- Network activity
- Services
- `sudo` commands

## Log Location

Most log files are stored under:

```text
/var/log/
```

> Log locations may vary depending on the Linux distribution, but they are generally similar.

---

## Common Logs (SOC POV)

| Log File | Purpose |
|----------|---------|
| `/var/log/auth.log` \| `/var/log/secure` | Login attempts, SSH, `sudo` activity |
| `/var/log/syslog` \| `/var/log/messages` | General system logs |
| `/var/log/dmesg` | Hardware and kernel boot messages |
| `/var/log/faillog` | Failed login attempts |
| `/var/log/lastlog` | Last login for each user |
| `/var/log/httpd/` \| `/var/log/nginx/` | Web server logs |
| `/var/log/apache2/` | Apache access and error logs |
| `/var/log/boot.log` | Boot-related events |
| `/var/log/cron` | Scheduled job execution |
| `/var/log/kern.log` | Kernel-related logs |
| `/var/log/btmp` | Failed login records (binary) |

---

## `/var/log/auth.log`

Useful for detecting:

- SSH login attempts (successful or failed)
- `sudo` activity
- Brute-force attacks
- Privilege abuse through `sudo`

PAM (Pluggable Authentication Modules) also logs authentication events here.

---

## Useful Commands

Find `sudo` usage:

```sh
grep "sudo" /var/log/auth.log
```

View successful SSH logins:

```sh
grep "Accepted" /var/log/auth.log
```

View failed login attempts:

```sh
faillog -a
```

Show failed logins stored in `/var/log/btmp`:

```sh
lastb
```

View login history (`/var/log/wtmp`):

```sh
last
```

View the last login for every user:

```sh
lastlog
```

View your own `sudo` history:

```sh
cat ~/.bash_history | grep sudo
```

Check system boot performance:

```sh
systemd-analyze blame
```

View cron executions:

```sh
grep CRON /var/log/syslog
```

View current cron jobs for root:

```sh
sudo crontab -l
```

---

## Notes

- Persistence malware can use **cron jobs** to maintain persistence, so always inspect cron entries during an investigation.
- `wtmp` stores successful login/logout history and is viewed using the `last` command.
- `btmp` stores failed login attempts and is viewed using the `lastb` command.

---
