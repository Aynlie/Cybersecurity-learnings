# Linux Basics — Building My First Lab VMs

| Field | Details |
|---|---|
| **Topic** | Linux Fundamentals — VM Setup & First Commands |
| **Tools** | VirtualBox, VMware Workstation, Ubuntu Server, Kali Linux |
| **Date** | August 2026 |
| **Status** | ✅ Ongoing |

---

## 🧩 Why I'm Doing This

Before touching any security tools, I needed to stop being someone who
"follows a lab" and start being someone who can sit at a blank Linux
terminal and actually operate it. This is Phase 1 of my 90-Day
Cybersecurity Employability Roadmap — Linux Independence.

---

## 🛠️ What I Built

I set up virtual machines across two computers to get real, repeated
reps with Linux installs and terminal use:

| Machine | Hypervisor | VMs |
|---|---|---|
| Laptop | VirtualBox | Ubuntu Server, Kali Linux |
| Desktop PC | VMware Workstation | Ubuntu Server, Kali Linux, Security Onion |

Each VM was installed manually — no unattended/auto-install — so I'd
actually see and understand every step: language, keyboard layout,
network config, disk partitioning, and user account creation.

---

## 🔍 My Thought Process

I didn't want a guided lab where someone else clicks the buttons for
me. So every VM I built, I made a rule: walk through the real
installer, type the real commands, and when something breaks — fix it
myself before asking for the answer.

That rule paid off almost immediately, because things *did* break.

---

## 🚩 Real Problems I Hit (and Fixed)

### Problem 1 — 403 Forbidden on `apt upgrade`

After my first Ubuntu Server install, running the standard update
command failed:

```bash
sudo apt update && sudo apt upgrade -y
```

```
Err:1 http://ph.archive.ubuntu.com/ubuntu resolute-updates/main amd64 ...
403  Forbidden [IP: 202.79.180.254 80]
Error: Unable to fetch some archives, maybe run apt-get update or try with --fix-missing?
```

The Philippines regional mirror (`ph.archive.ubuntu.com`) was
rejecting requests for a specific package. I found the real source
file and swapped it to the global mirror:

```bash
sudo sed -i 's/ph.archive.ubuntu.com/archive.ubuntu.com/g' /etc/apt/sources.list.d/ubuntu.sources
sudo apt update
sudo apt upgrade -y
```

**Lesson:** on newer Ubuntu versions, `/etc/apt/sources.list` is often
empty — the real mirror config lives in
`/etc/apt/sources.list.d/ubuntu.sources` instead.

### Problem 2 — Same mirror issue, mid-install this time

On my second machine, the exact same mirror caused the *installer
itself* to crash during the package step (not just later during
upgrade). Fix: on the "Ubuntu archive mirror configuration" screen
during install, I replaced the mirror address directly:

```
http://archive.ubuntu.com/ubuntu/
```

**Lesson:** the same root cause can surface at different points
depending on when the system tries to reach the network — always
check the mirror first if a fresh Ubuntu install fails partway
through package installation.

### Problem 3 — Security Onion disk too small

```
Not enough space to install Security Onion. You need at least 99 GB to proceed
```

I'd sized the disk at 60 GB based on a rough estimate. Real
requirement: 99 GB minimum. Rebuilt the VM with 120 GB to leave
headroom for logs.

**Lesson:** always check a tool's *actual* documented minimum specs
before provisioning — don't guess based on what "feels like enough."

---

## 📚 What I Learned

### 1. Where package sources actually live
```bash
cat /etc/apt/sources.list.d/ubuntu.sources
```
Modern Ubuntu (24.04+) uses the deb822 format in this file instead of
the old flat `/etc/apt/sources.list`.

### 2. `sed` for in-place file editing
```bash
sudo sed -i 's/find-this/replace-with-this/g' /path/to/file
```
`-i` edits the file in place, `s/.../.../g` is a find-and-replace —
`g` means replace every occurrence, not just the first.

### 3. First commands to confirm you're actually "in"
```bash
whoami   # confirms which user you're logged in as
pwd      # confirms your current directory
ls -la   # lists all files, including hidden ones, with full details
```

### 4. Disk partitioning basics
- "Use entire disk" + LVM group = flexible, resizable partitions later
- LUKS encryption = full-disk encryption, adds a passphrase every boot
  (skipped for lab VMs — not needed when there's no sensitive data)

---

## 💡 Key Takeaway

> The install never went perfectly the first time — and that's
> exactly what made it worth doing manually. Reading a real error,
> tracing it to its actual cause, and fixing it myself is a more
> useful rep than an install that goes smoothly on rails.

---

## 🔗 Resources

- [Ubuntu Server Downloads](https://ubuntu.com/download/server)
- [Kali Linux Downloads](https://www.kali.org/get-kali/)
- [Security Onion](https://securityonion.net/)
- [VirtualBox](https://www.virtualbox.org/)
- [VMware Workstation](https://www.vmware.com/products/workstation-pro.html)

---

*Notes by Jaymee J. Santos | BS Cybersecurity, Holy Angel University 🇵🇭*
*"When you try, you already overcome it."*