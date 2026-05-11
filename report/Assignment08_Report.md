# Assignment 08 Report — Draft (Markdown)

> You can write your report in Markdown here and export to PDF/DOCX later.

## Title

Assignment 08 — Decrypt Given Passwords (Hash Analysis & Password Cracking Documentation)

## Objective

Identify hash types and document password recovery attempts using **approved lab-only methods**.

## Hash Identification Table

| Hash | Detected/Probable Hash Type | Evidence/Reasoning |
|------|-----------------------------|--------------------|
| 161ebd7d45089b3446ee4e0d86dbcf92 | MD5 (32‑hex) | `hashid` output lists MD5; 32 hex chars. (see `report/figures/hashid_output.png`) |
| 0e7517141fb53f21ee439b355b5a1d0a | MD5 (32‑hex) | `hashid` output lists MD5; 32 hex chars. (see `report/figures/hashid_output.png`) |
| 94ad8aec4ddc6479c6e4528649d9f3dd | MD5 (32‑hex) | `hashid` output lists MD5; 32 hex chars. (see `report/figures/hashid_output.png`) |
| 63a9f0ea7bb98050796b649e85481845 | MD5 (32‑hex) | `hashid` output lists MD5; 32 hex chars. (see `report/figures/hashid_output.png`) |
| 5858ea228cc2edf88721699b2c8638e5 | MD5 (32‑hex) | `hashid` output lists MD5; 32 hex chars. (see `report/figures/hashid_output.png`) |
| 56367964541f60461ba7a36b8d7539b7 | MD5 (32‑hex) | `hashid` output lists MD5; 32 hex chars. (see `report/figures/hashid_output.png`) |

## Cracking Results Table

| Hash | Result (Cracked/Uncracked) | Plaintext (if cracked) | Evidence |
|------|-----------------------------|-------------------------|---------|
| 161ebd7d45089b3446ee4e0d86dbcf92 | Cracked | Passw0rd | `report/figures/final_results.png` |
| 0e7517141fb53f21ee439b355b5a1d0a | Cracked | Admin@123 | `report/figures/final_results.png` |
| 94ad8aec4ddc6479c6e4528649d9f3dd | Uncracked |  | `report/figures/final_results.png` |
| 63a9f0ea7bb98050796b649e85481845 | Cracked | root | `report/figures/final_results.png` |
| 5858ea228cc2edf88721699b2c8638e5 | Cracked | welcome123 | `report/figures/final_results.png` |
| 56367964541f60461ba7a36b8d7539b7 | Cracked | CYBERSECURITY | `report/figures/final_results.png` |

## Methodology

- **Tools used:** hashid (hash identification), hashcat (installed), custom wordlist (`wordlist.txt`).
- **Hash identification approach:** Used `hashid` to classify each 32‑hex hash and recorded the likely type (MD5).
- **Recovery approach:** Lab‑approved wordlist attempt using `wordlist.txt`.
- **Time taken:** Recorded during lab execution.
- **Evidence:** `report/figures/hashid_output.png`, `report/figures/wordlist.png`, `report/figures/final_results.png`.

## Security Analysis

- Which hashes were easiest to crack and why?
- Which were hardest and why?
- What characteristics make passwords strong/weak?

## Risk Assessment

- Account takeover risks
- Data breach impact
- Credential reuse and lateral movement

## Recommendations

- Strong password policy guidance
- Use of salted, slow hashing (bcrypt/Argon2/scrypt)
- Secure storage practices

## Conclusion

Summarize outcomes, lessons learned, and key security takeaways.
