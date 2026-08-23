# Fantasy CTF

| Field | Details |
|---|---|
| **Platform** | PicoCTF — picoGym |
| **Category** | General Skills |
| **Points** | 25 |
| **Difficulty** | Easy |
| **Date Solved** | April 6, 2026 |
| **Status** | ✅ Solved |

---

## 🧩 Challenge Description

> "Welcome, hero. The digital kingdom is under threat. Answer wisely and the flag shall be yours."
>
> Navigate through a fantasy simulation by answering cybersecurity questions correctly. Reach the end and run the given command to retrieve the flag.

---

## 📁 Files Given

| File | Description |
|---|---|
| `fantasy_ctf` | Executable that runs the simulation and reveals the flag |

---

## 🛠️ Tools Used

- PicoCTF Webshell — [webshell.picoctf.org](https://webshell.picoctf.org)
- `wget` — to download the challenge binary
- `chmod` — to make the file executable
- `./fantasy_ctf --reveal-flag` — to retrieve the flag after completing the simulation

---

## 🔍 My Thought Process

When I opened the challenge I saw it was a story-driven simulation. Instead of finding a hidden file or decoding something, I had to **answer questions correctly** to advance the story. Each wrong answer sent me back to retry. I realized:

1. The questions were all based on real cybersecurity concepts
2. Correct answers = story progresses
3. Completing all questions unlocks a terminal command that prints the flag

---

## 🚩 Step-by-Step Solution

### Step 1 — Open PicoCTF Webshell
Went to [webshell.picoctf.org](https://webshell.picoctf.org) and logged in with my PicoCTF account.

### Step 2 — Download the challenge file using wget
Right-clicked the download link on the challenge page → copied the link address → used wget:

```bash
wget https://artifacts.picoctf.net/c/fantasy/fantasy_ctf
```

### Step 3 — Make the file executable
```bash
chmod +x fantasy_ctf
```

### Step 4 — Run the simulation
```bash
./fantasy_ctf
```

Output:
```
Welcome, hero. The digital kingdom awaits.
Answer correctly to advance your quest...
```

### Step 5 — Answer the questions

The simulation presented 5 questions. I read each scenario carefully and chose the correct answer.

---

**Question 1:** The kingdom's gate is locked. What is the first thing a defender should always do when joining a new system?

- A) Install antivirus immediately
- B) Change all passwords at random
- **C) Audit existing users and permissions** ✅
- D) Reboot the server

```
✅ Correct! The gate opens...
```

---

**Question 2:** A messenger arrives with a suspicious scroll. What type of attack does this represent?

- A) DDoS attack
- B) SQL Injection
- **C) Phishing / social engineering** ✅
- D) Brute force

```
✅ Correct! You see through the deception...
```

---

**Question 3:** The castle walls have a hidden passage. In cybersecurity, what do we call an unintended entry point into a system?

- A) Firewall
- B) Exploit
- **C) Vulnerability** ✅
- D) Patch

```
✅ Correct! The passage is sealed...
```

---

**Question 4:** The wizard encrypts a message using a key only the recipient has. What encryption type is this?

- A) Symmetric encryption
- **B) Asymmetric encryption** ✅
- C) Hashing
- D) Encoding

```
✅ Correct! The wizard nods in approval...
```

---

**Question 5 (Final):** You have reached the final chamber. The ancient scroll says: "The one who defends must always watch the logs." What tool does a SOC analyst use to monitor logs centrally?

- A) Wireshark
- B) Nmap
- C) Metasploit
- **D) SIEM (Security Information and Event Management)** ✅

```
✅ Correct! Quest complete. Run the command to claim your flag.
```

---

### Step 6 — Run the flag command
The simulation revealed the final command:

```bash
./fantasy_ctf --reveal-flag
```

Output:
```
picoCTF{f4nt4sy_qu3st_c0mpl3t3d_a9f2c814}
```

### Step 7 — Submitted the flag
Went back to the PicoCTF challenge page → pasted the flag → clicked Submit ✅

---

## 🏁 Flag

```
picoCTF{f4nt4sy_qu3st_c0mpl3t3d_a9f2c814}
```

---

## 📚 What I Learned

### 1. Blue team fundamentals show up everywhere
Even in a story-based challenge, the questions tested real defender knowledge:
- Auditing users and permissions before anything else
- Recognizing phishing as social engineering
- Understanding the difference between vulnerabilities and exploits

### 2. Asymmetric vs symmetric encryption
```
Symmetric:    Same key encrypts AND decrypts   →   faster, used for bulk data
Asymmetric:   Public key encrypts, private key decrypts   →   used in HTTPS, SSH, email
```

### 3. What a SIEM does
```
Logs from firewall  ──┐
Logs from servers   ──┤──→  SIEM  ──→  Alerts + dashboards for SOC analyst
Logs from endpoints ──┘
```
A SIEM collects, normalizes, and correlates logs from across an entire environment so analysts can detect threats in one place. Key tools: Splunk, Microsoft Sentinel, IBM QRadar.

### 4. The `chmod +x` command
```bash
chmod +x filename
```
Makes a file executable — required before you can run a downloaded binary with `./filename`. Without it you get a "Permission denied" error.

### 5. Story-based CTFs still need real knowledge
> Don't let the narrative distract you. Strip the story down to the core question and answer from your actual cybersecurity knowledge — not the most dramatic-sounding option.

---

## 💡 Key Takeaway

> SOC analysts, incident responders, and blue teamers use every concept tested in this challenge daily — auditing access, spotting phishing, identifying vulnerabilities, understanding encryption, and monitoring logs through a SIEM. Fantasy wrapper, real skills.

---

## 🔗 Resources

- [PicoCTF Fantasy CTF Challenge](https://picoctf.org)
- [PicoCTF Webshell](https://webshell.picoctf.org)
- [OWASP — Vulnerabilities explained](https://owasp.org)
- [CyberChef — for encoding/decoding](https://gchq.github.io/CyberChef)
- [TryHackMe — SOC Level 1 Path](https://tryhackme.com)

---

*Writeup by Jaymee J. Santos | BS Cybersecurity, Holy Angel University 🇵🇭*

* P.S Just continue it guys hehee and choose the right answers *
## SO Bery Easy
