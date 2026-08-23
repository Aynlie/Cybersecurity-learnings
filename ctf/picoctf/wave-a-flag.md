# Wave a Flag

| Field | Details |
|---|---|
| **Platform** | PicoCTF — picoGym |
| **Category** | General Skills |
| **Points** | 10 |
| **Difficulty** | Easy |
| **Date Solved** | April 6, 2026 |
| **Status** | ✅ Solved |

---

## 🧩 Challenge Description

> "Can you invoke help flags for a tool?"
>
> Download the program and run it with a help flag to get the flag.

---

## 📁 Files Given

| File | Description |
|---|---|
| `warm` | Executable program that outputs the flag when given the `-h` argument |

---

## 🛠️ Tools Used

- PicoCTF Webshell — [webshell.picoctf.org](https://webshell.picoctf.org)
- `wget` — to download the challenge binary
- `chmod` — to make the file executable
- `-h` flag — help argument passed to the program

---

## 🔍 My Thought Process

The challenge is called **"Wave a Flag"** — in Linux, a "flag" can mean two things:
1. The CTF secret code we're looking for (`picoCTF{...}`)
2. An **argument** passed to a program (like `-h`, `--help`, `-v`)

The challenge title was a hint. I needed to run the program and pass it the `-h` flag (help argument) to make it reveal the CTF flag.

---

## 🚩 Step-by-Step Solution

### Step 1 — Open PicoCTF Webshell
Went to [webshell.picoctf.org](https://webshell.picoctf.org) and logged in with my PicoCTF account.

### Step 2 — Download the file using wget
Right-clicked the download link on the challenge page → copied the link address → used wget:

```bash
wget https://challenge-files.picoctf.net/c_wily_courier/11d04620d1b8e59680f745f5e3d3957d48628b1e3e7c56c74c0030e82a778d63/warm
```

### Step 3 — Confirm the file downloaded
```bash
ls
```

Output:
```
README.txt  ende.py  flag.txt.en  password.txt  warm  warm.1  warm.2  wget-log
```

### Step 4 — Make the file executable
```bash
chmod +x warm
```

### Step 5 — Run the program
```bash
./warm
```

Output:
```
Hello user! Pass me a -h to learn what I can do!
```

The program itself told me what to do next — pass it `-h`.

### Step 6 — Run with the `-h` flag
```bash
./warm -h
```

Output:
```
Oh, help? I actually don't do much, but I do have this flag here: picoCTF{b1scu1ts_4nd_gr4vy_ac5832c}
```

### Step 7 — Submitted the flag
Went back to the PicoCTF challenge page → pasted the flag → clicked Submit ✅

---

## 🏁 Flag

```
picoCTF{b1scu1ts_4nd_gr4vy_ac5832c}
```

---

## 📚 What I Learned

### 1. What `-h` means
`-h` is a **help flag** — an argument you pass to a program to ask it what it does.

Almost every Linux program supports it:
```bash
python3 -h
wget -h
chmod -h
```

It's one of the first things to try when you don't know how a program works.

### 2. The double meaning of "flag" in CTF
| Context | Meaning |
|---|---|
| CTF flag | The secret code — `picoCTF{...}` |
| Linux flag | An argument passed to a program — `-h`, `-d`, `-v` |

The challenge title "Wave a Flag" was a pun — you had to use a Linux flag (`-h`) to get the CTF flag.

### 3. `chmod +x` makes a file runnable
```bash
chmod +x warm    # give execute permission
./warm           # now you can run it
```
Downloaded files are not executable by default in Linux. You always need `chmod +x` before running a downloaded program.

### 4. Programs can guide you
When `./warm` said "Pass me a -h to learn what I can do!" — that was the program telling me exactly what to do next. Always read the output carefully, even error messages and hints are useful.

---

## 💡 Key Takeaway

> In real security work, reading documentation and help outputs is essential. Tools like `nmap`, `openssl`, and `metasploit` all have `-h` or `--help` flags that explain their usage. Getting comfortable with help flags early builds good habits for using professional security tools later.

---

## 🔗 Resources

- [PicoCTF Wave a Flag Challenge](https://picoctf.org)
- [PicoCTF Webshell](https://webshell.picoctf.org)
- [Linux chmod explained](https://linux.die.net/man/1/chmod)
- [CyberChef — for encoding/decoding](https://gchq.github.io/CyberChef)

---

*Writeup by Jaymee J. Santos | BS Cybersecurity, Holy Angel University 🇵🇭*
*"When you try, you already overcome it."*

* Nung una I was like ahh why there's nothing running then parang may access needed or there's firewall inside of the webshell then I use chmod + x*
* then omyghod before I run then so I make sure na download so I typed ls and there it is naging tatlo pa dinownload ko whahaha lame*
* then there's a pop up thingy so I click -h cuz that's the statement says eh ano vha?? but ayun no file directory ermm okay? then I type what if
* ./warm -h*
* boom nandiyan na ang flag so bery easy*
