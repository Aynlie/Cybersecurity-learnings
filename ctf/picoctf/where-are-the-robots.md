# picoCTF: where are the robots

| Field | Details |
| :--- | :--- |
| **Platform** | picoCTF |
| **Category** | Web Exploitation |
| **Points** | 100 |
| **Date Completed** | August 28, 2026 |
| **Flag** | `picoCTF{ca1culat1ng_Mach1n3s_cc6b1}` |
| **Status** | ✅ Solved |

---

## 📌 Challenge Overview
The challenge presents a landing page asking *"Where are the robots?"*, hinting at the standard web crawler exclusion standard (`robots.txt`).

---

## 🔍 Solution Walkthrough

1. **Reconnaissance & Crawler Policy Check:**
   Queried the root `/robots.txt` endpoint to inspect disallowed routes:
   ```bash
   curl [http://fickle-tempest.picoctf.net:58739/robots.txt](http://fickle-tempest.picoctf.net:58739/robots.txt)

Output:

User-agent: *
Disallow: /cc6b1.html

Fetching the Disallowed Endpoint:
Navigated directly to the hidden endpoint identified in the crawler policy:

Bash: curl [http://fickle-tempest.picoctf.net:58739/cc6b1.html](http://fickle-tempest.picoctf.net:58739/cc6b1.html)

Flag Extraction:
The HTML response contains the flag embedded within <flag> tags:
<p>Guess you found the robots<br />
<flag>picoCTF{ca1culat1ng_Mach1n3s_cc6b1}</flag></p>

Key Takeaways
Information Disclosure: robots.txt is publicly accessible and is intended to instruct well-behaved web crawlers which pages not to index, but it is not an access-control mechanism.

Security Through Obscurity: Relying on hidden URLs listed in crawler files exposes sensitive endpoints to simple reconnaissance.