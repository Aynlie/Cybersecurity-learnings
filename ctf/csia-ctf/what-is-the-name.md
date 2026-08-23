# What is the name?

| Field | Details |
|---|---|
| **Platform** | CSIA CTF — haucsia.com |
| **Category** | Binary Exploitation |
| **Points** | 50 |
| **Difficulty** | Easy |
| **Date Solved** | April 6, 2026 |
| **Status** | ✅ Solved |

---

## 🧩 Challenge Description

> "Choose any of these ten usernames:"
> - hunter1
> - hunter2
> - hunter3
> - hunter4
> - hunter5
> - hunter6
> - hunter7
> - hunter8
> - hunter9
> - hunter10

---

## 🛠️ Tools Used

- Kali Linux terminal
- `nc` (netcat) — to connect to the challenge server

---

## 🔍 My Thought Process

The challenge gave me ten possible usernames and said to "choose any." That sounded too easy — I suspected only **one specific username** was actually correct and the rest would be rejected. The challenge is called **"What is the name?"** which hinted there is one right answer hidden among the ten options.

My plan:
1. Connect to the server using `nc`
2. Try the usernames one by one starting from `hunter1`
3. Stop when the server accepts one and returns the flag

---

## 🚩 Step-by-Step Solution

### Step 1 — Launch the instance
Clicked **LAUNCH** on the challenge page to spin up an isolated server instance. It gave me the connection details:

```
nc andrew.chal.haucsia.com 10031
```

### Step 2 — Connect using netcat from Kali Linux
Opened my Kali Linux terminal and ran:

```bash
nc andrew.chal.haucsia.com 10031
```

Output:
```
Welcome! What's the secret word?
```

### Step 3 — Tried hunter1
```
hunter1
```

Output:
```
Wrong.
```

### Step 4 — Connected again and tried hunter2
Netcat closes after a wrong answer so I reconnected:

```bash
nc andrew.chal.haucsia.com 10031
```

Output:
```
Welcome! What's the secret word?
```

Typed:
```
hunter2
```

Output:
```
CSIA{d48d3319658583b9f830c82743548e8f06bbe7a29508090107c34c13d01eca41}
```

### Step 5 — Submitted the flag
Went back to the CSIA CTF challenge page → pasted the flag → clicked Submit ✅

---

## 🏁 Flag

```
CSIA{d48d3319658583b9f830c82743548e8f06bbe7a29508090107c34c13d01eca41}
```

---

## 📚 What I Learned

### 1. What `nc` (netcat) is
`nc` stands for **netcat** — it's a networking tool that lets you connect to a server and send/receive text directly through the terminal. It's one of the most used tools in CTF.

```bash
nc <host> <port>
```

Think of it like knocking on a door at a specific address (`host`) and room number (`port`). The server answers and you have a live conversation.

### 2. "Choose any" doesn't always mean any
The challenge description said "choose any of these ten usernames" — but that was misleading. Only one username was actually correct. Always test each option when a challenge gives you a list like this.

### 3. Netcat closes the connection after a wrong answer
Each time I got "Wrong." the connection dropped and I had to reconnect with `nc` again before trying the next username. This is common in CTF server challenges.

### 4. I used Kali Linux — not the Webshell
This was my first challenge solved directly from **Kali Linux on my own laptop** instead of the PicoCTF Webshell. Both work the same way for `nc` commands — Kali just gives me more tools and flexibility.

### 5. Enumeration is a core skill
Trying options one by one in a systematic order (`hunter1` → `hunter2` → ...) is called **enumeration** — a fundamental technique in cybersecurity. Real penetration testers enumerate usernames, ports, directories, and passwords the same way.

---

## 💡 Key Takeaway

> Don't take challenge descriptions at face value. "Choose any" turned out to mean "find the right one." Reading carefully and testing systematically — that's enumeration, and it's one of the most important skills in both CTF and real-world security work.

---

## 🔗 Resources

- [CSIA CTF Platform](https://haucsia.com)
- [Netcat explained — HackTricks](https://book.hacktricks.xyz)
- [TryHackMe — Linux Fundamentals](https://tryhackme.com)

---

*Writeup by Jaymee J. Santos | BS Cybersecurity, Holy Angel University 🇵🇭*
*"When you try, you already overcome it."*

*Nung una I tried in webshell picoctf then there's nothing happened maybe because they have different platform or what*
*then I tried on my own linux wbeshell then there's pop up says na "welcome what's the secret word?*
*then I type first is hunter1 nge wrong*
*then I type next is hunter2, there's a flah yey!*
