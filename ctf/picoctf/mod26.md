# picoCTF: Mod 26

| Field | Details |
| :--- | :--- |
| **Platform** | picoCTF |
| **Category** | Cryptography |
| **Points** | 10 |
| **Date Completed** | August 24, 2026 |
| **Status** | ✅ Solved |

---

## 📌 Description
Cryptography can often be easy, do you know what ROT13 is? `cvpbPGS{arkg_gvzr_V'yy_gel_2_ebhaqf_bs_ebg13_45559noq}`

---

## 🔍 Solution Steps
1. **Initial Analysis:** The challenge presents a ciphertext formatted like a flag and references ROT13 (Rotate by 13 places), a symmetric substitution cipher based on modulo 26.
2. **Execution / Decoding:** 
   - Loaded the ciphertext into CyberChef.
   - Applied the `ROT13` recipe (13-character rotation).
3. **Flag Recovery:** 
   `picoCTF{next_time_I'll_try_2_rounds_of_rot13_45559abd}`

---

## 💡 Key Takeaways
* Reinforced how Caesar / ROT13 substitution ciphers function across a 26-letter alphabet.
* Non-alphabetic characters, numbers, and symbols are preserved during character rotation.