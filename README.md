# Kali Linux Lab
Automated Kali Linux VM built with Vagrant and VMware Workstation Pro.
The environment comes pre-configured with pentest tools and basic hardening.

## Includes

**Pentest Tools**
- Kali Linux rolling release with default tools (nmap, metasploit, burpsuite etc.)
- gobuster, ffuf — web fuzzing and directory brute-force
- crackmapexec, impacket — Active Directory and Windows testing
- evil-winrm — Windows remote management
- amass, subfinder — subdomain enumeration and reconnaissance
- seclists — wordlists for brute-force and fuzzing

**Hardening**
- UFW firewall — blocks all incoming traffic
- Fail2ban — brute-force protection
- Auditd — system logging
- SSH hardening — root login disabled, max 3 login attempts
- Unnecessary services disabled (bluetooth, cups, avahi)

**Other**
- OpenVPN — support for TryHackMe and HackTheBox
- VMware Guest Additions — clipboard sharing, screen resolution

## Requirements

- [Vagrant](https://www.vagrantup.com/)
- [VMware Workstation Pro](https://www.vmware.com/products/workstation-pro.html)
- [vagrant-vmware-desktop plugin](https://developer.hashicorp.com/vagrant/docs/providers/vmware)

## Installation

### 1. Install Vagrant VMware plugin
```bash
vagrant plugin install vagrant-vmware-desktop
```

### 2. Clone the repository
```bash
git clone https://github.com/Sav1cc/Kali-lab.git
cd Kali-lab
```

### 3. Start the VM
```bash
vagrant up
```
First boot takes 10-20 minutes depending on your internet connection.

### 4. After startup
Log in via VMware GUI with:
- Username: `kali`
- Password: `kali`

Change passwords immediately:
```bash
passwd kali
passwd root
```

## Commands
```bash
vagrant up        # Start the VM
vagrant halt      # Shut down the VM
vagrant suspend   # Suspend the VM
vagrant destroy   # Delete the VM completely
vagrant provision # Re-run provisioning
```

## Disclaimer
This VM is intended for legal pentesting in controlled environments such as TryHackMe and HackTheBox.
Never use these tools against systems you do not have explicit permission to test.
