## Caesar

**Category:** Cryptography
**Points:** 100
**Date:** April 8, 2026
**Status:** ✅ Solved

### Challenge
A message has been encrypted using a Caesar cipher. Decrypt the ciphertext to find the flag.

**Ciphertext:**
```
picoCTF{bqnrrhmfsgdqtahbnmphkgrwqj}
```

### Solution
1. Recognized the encryption as a Caesar cipher (simple letter shift)
2. Since the shift is unknown, brute forced all 25 possible shifts
3. Used the formula for each letter:
   ```
   decrypted = (letter_position - shift) mod 26
   ```
4. Wrote a Python script to test all shifts:
   ```python
   cipher = 'bqnrrhmfsgdqtahbnmphkgrwqj'
   for shift in range(1, 26):
       decrypted = ''
       for c in cipher:
           if c.isalpha():
               decrypted += chr((ord(c) - ord('a') - shift) % 26 + ord('a'))
           else:
               decrypted += c
       print(f'Shift {shift}: {decrypted}')
   ```
5. Shift 25 produced readable English: `crossingtherubiconqilhsxrk`
6. Recognized the phrase **"crossing the rubicon"** — meaning a point of no return 🎯

### What I Learned
Caesar cipher works by shifting each letter by a fixed number. To decrypt, you shift **backwards** by the same amount. Since the shift is unknown, you can **brute force** all 25 possibilities and look for the one that produces readable English.

The formula:
```
decrypted_letter = (position - shift) mod 26
```

**Shortcut for next time:** Use [CyberChef](https://gchq.github.io/CyberChef) → search `ROT13 Brute Force` → paste ciphertext → find the readable output!

### Personal Note
At first I had no idea what shift to use — there are 25 possibilities! But brute forcing all of them with a simple Python loop made it easy. The hidden phrase "crossing the rubicon" was a cool touch by the challenge makers. Caesar cipher seems simple but it's a great intro to understanding how encryption and decryption actually work.

### Flag
```
picoCTF{crossingtherubiconqilhsxrk}
```
