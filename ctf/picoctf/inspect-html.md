# picoCTF: Inspect HTML

| Field | Details |
| :--- | :--- |
| **Platform** | picoCTF |
| **Category** | Web Exploitation |
| **Date Completed** | August 24, 2026 |
| **Status** | ✅ Solved |

---

## 📌 Description
Can you get the flag? Go to this website and see what you can discover.

---

## 🔍 Solution Steps
1. **Initial Analysis:** Opened the challenge link in the web browser.
2. **Execution:** Pressed `Ctrl + U` (or right-clicked and selected **View Page Source**) to examine the raw client-side HTML structure.
3. **Flag Recovery:** Scanned the embedded HTML comments to extract the hidden flag string:
   `picoCTF{1n5p3t0r_0f_h7ml_8113f7e2}`

---

## 💡 Key Takeaways
* Viewing page source (`Ctrl + U`) is an essential baseline step in web analysis for uncovering client-side comments, hidden elements, and endpoints.
* Sensitive strings or comments should never be left in public client-facing production code.