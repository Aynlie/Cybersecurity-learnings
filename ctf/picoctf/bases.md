# picoCTF: Bases

| Field | Details |
| :--- | :--- |
| **Platform** | picoCTF |
| **Category** | General Skills |
| **Points** | 100 |
| **Date Completed** | August 24, 2026 |
| **Status** | ✅ Solved |

---

## 📌 Description
What does this `bDNhcm5fdGgzX3IwcDM1` mean? I think it has something to do with bases.

---

## 🔍 Solution Steps
1. **Initial Analysis:** The provided string contains alphanumeric characters matching the Base64 character set (length of 20 characters, a multiple of 4).
2. **Execution / Decoding:** 
   - Loaded the string `bDNhcm5fdGgzX3IwcDM1` into CyberChef.
   - Applied the `From Base64` recipe to decode the ciphertext back to plaintext.
   - Extracted the decoded payload: `l3arn_th3_r0p35`
3. **Flag Recovery:** Wrapped the decoded text into standard picoCTF flag syntax:
   `picoCTF{l3arn_th3_r0p35}`

---

## 💡 Key Takeaways
* Understood the difference between encoding (`To Base64`) and decoding (`From Base64`).
* Identified Base64 strings by character constraints (A-Z, a-z, 0-9, +, /) and length divisibility by 4.