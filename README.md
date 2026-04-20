# Kali Linux Lab

Automatiserad Kali Linux VM byggd med Vagrant och VMware Workstation Pro.
Miljön är förkonfigurerad med pentestverktyg och grundläggande härdning.

## Innehåller

**Pentestverktyg**
- Kali Linux rolling release med standardverktyg (nmap, metasploit, burpsuite m.fl.)
- gobuster, ffuf — webbfuzzing och katalogbrute-force
- crackmapexec, impacket — Active Directory och Windows-testning
- evil-winrm — Windows remote management
- amass, subfinder — subdomänsökning och rekognosering
- seclists — ordlistor för brute-force och fuzzing

**Härdning**
- UFW brandvägg — blockerar all inkommande trafik
- Fail2ban — skydd mot brute-force
- Auditd — systemloggning
- SSH-härdning — root-login blockerat, max 3 inloggningsförsök
- Onödiga tjänster inaktiverade (bluetooth, cups, avahi)

**Övrigt**
- OpenVPN — stöd för TryHackMe och HackTheBox
- VMware Guest Additions — klipp-och-klistra, skärmupplösning

## Krav

- [Vagrant](https://www.vagrantup.com/)
- [VMware Workstation Pro](https://www.vmware.com/products/workstation-pro.html)
- [vagrant-vmware-desktop plugin](https://developer.hashicorp.com/vagrant/docs/providers/vmware)

## Installation

### 1. Installera Vagrant VMware plugin
```bash
vagrant plugin install vagrant-vmware-desktop
```

### 2. Klona repot
```bash
git clone https://github.com/Sav1cc/kali.git
cd kali
```

### 3. Starta VM:en
```bash
vagrant up
```
Första uppstarten tar 5-10 minuter beroende på internetanslutning.

### 4. Efter uppstart
Logga in via VMware GUI med:
- Användare: `vagrant`
- Lösenord: `vagrant`

Byt lösenord direkt:
```bash
passwd kali
```

## Kommandon

```bash
vagrant up        # Starta VM:en
vagrant halt      # Stäng av VM:en
vagrant suspend   # Pausa VM:en
vagrant destroy   # Radera VM:en helt
vagrant provision # Kör om provisioneringen
```

## Säkerhet

Denna VM är avsedd för laglig pentesting i kontrollerade miljöer såsom TryHackMe och HackTheBox.
Använd aldrig dessa verktyg mot system du inte har tillstånd att testa.