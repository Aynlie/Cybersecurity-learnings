## Who Lives, Who Dies, Who Tells Your Story

**Category:** Cryptography
**Difficulty:** Easy
**Points:** 50
**Date:** April 9, 2026
**Status:** Solved

### Challenge
A string is given. Decode it to find the flag.

**Ciphertext:**
```
Q1NJQXtoYW1pbHRvbl9pc190aHJvd2luZ19hd2F5X215X3Nob3R9
```

### How I Recognized It Was Base64
Before decoding, I identified it as Base64 by checking:

1. **Character set** — only contains `A-Z`, `a-z`, `0-9`, `+`, `/`, `=`. No weird symbols.
2. **Length** — Base64 strings are always a multiple of 4 characters (padded with `=`)
3. **Looks almost readable** — not pure chaos like real encryption
4. **Context** — Easy cryptography + 50 points = almost always Caesar or Base64

### Quick Encoding Recognition Cheat Sheet
| Pattern | Encoding |
|---------|----------|
| Only letters + numbers + `/+=` | Base64 |
| Only letters, shifted alphabet | Caesar / ROT13 |
| Only `0-9` and `A-F` | Hexadecimal |
| Contains `%2F`, `%20` | URL encoding |
| Dots and dashes | Morse code |

### Solution

**Method 1 — Linux / Kali terminal (fastest):**
```bash
echo "Q1NJQXtoYW1pbHRvbl9pc190aHJvd2luZ19hd2F5X215X3Nob3R9" | base64 -d
```

**Method 2 — Python (works everywhere):**
```python
import base64
print(base64.b64decode('Q1NJQXtoYW1pbHRvbl9pc190aHJvd2luZ19hd2F5X215X3Nob3R9').decode())
```

**Method 3 — PowerShell (Windows):**
```powershell
[System.Text.Encoding]::UTF8.GetString([System.Convert]::FromBase64String("Q1NJQXtoYW1pbHRvbl9pc190aHJvd2luZ19hd2F5X215X3Nob3R9"))
```

**Method 4 — CyberChef:**
1. Go to gchq.github.io/CyberChef
2. Search operation: `From Base64`
3. Paste ciphertext → flag appears instantly

**Output:**
```
CSIA{hamilton_is_throwing_away_my_shot}
```

### What I Learned
Base64 is an **encoding scheme**, NOT encryption. The difference:
- **Encoding** — transforms data into another format. Reversible with no key needed.
- **Encryption** — scrambles data using a key. You need the key to reverse it.

Base64 is used everywhere in real life — email attachments, image embedding in HTML, API tokens, and JWTs. It's not secure on its own because anyone can decode it instantly!

**Encode vs Decode:**
```bash
# Encode
echo "hello world" | base64
# Output: aGVsbG8gd29ybGQK

# Decode
echo "aGVsbG8gd29ybGQK" | base64 -d
# Output: hello world
```

### Personal Note
The title "Who lives, who dies, who tells your story" is from the Hamilton musical 🎭 and the flag contains "hamilton_is_throwing_away_my_shot" — a reference to the song *My Shot*. Love when CTF challenge makers put effort into the theme! Also learned that `base64 -d` is a Linux command and doesn't work in PowerShell — always use Kali for CTFs! 🐧

### Flag
```
CSIA{hamilton_is_throwing_away_my_shot}
```
