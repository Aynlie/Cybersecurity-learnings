# picoCTF: Includes

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
1. **Initial Analysis:** Launched the challenge webpage and accessed Developer Tools (`F12` / `Ctrl+U`) to trace all referenced external assets.
2. **Asset Inspection:** 
   - Inspected the linked stylesheet (`style.css`) to retrieve part 1 of the flag from the developer comments: `picoCTF{1nclu51v17y_1of2_`
   - Inspected the linked JavaScript file (`script.js`) to retrieve part 2 of the flag from the developer comments: `f7w_2of2_df589022}`
3. **Flag Recovery:** Concatenated both halves to construct the full flag:
   `picoCTF{1nclu51v17y_1of2_f7w_2of2_df589022}`

---

## 💡 Lessons Learned & SOC Triangulation
* **The "Where" in Incident Response:** Linked client-side source inspection directly to the **5 Ws** of SOC triage—identifying the exact origin file or asset path where artifacts reside is critical for both web assessments and alert investigations.
* **Separation of Concerns:** External `.css` and `.js` dependencies are served directly to the client browser in plaintext and must be audited for exposed sensitive data.