# Assignment 08 Report — Draft (Markdown)

> You can write your report in Markdown here and export to PDF/DOCX later.

## Title

Assignment 08 — Decrypt Given Passwords (Hash Analysis & Password Cracking Documentation)

## Objective

Identify the hash types for the provided values and document password recovery attempts using **approved lab‑only methods**. The goal is to demonstrate how weak passwords are exposed by common wordlists and to summarize the security implications and mitigation steps.

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
- **Hash identification approach:** Used `hashid` to classify each 32‑hex hash and recorded the likely type (MD5). Evidence captured in `report/figures/hashid_output.png`.
- **Recovery approach:** Lab‑approved wordlist attempt using `wordlist.txt`. Wordlist contents documented in `report/figures/wordlist.png`. Final outcomes captured in `report/figures/final_results.png`.
- **Time taken:** Recorded during lab execution.

## Evidence / Figures

- **Figure 1:** `report/figures/hashid_output.png` — hash identification output.
- **Figure 2:** `report/figures/wordlist.png` — custom wordlist contents.
- **Figure 3:** `report/figures/final_results.png` — final recovery results summary.

## Security Analysis

- **Easiest to crack:** Hashes that matched common words or patterns in the wordlist (e.g., `Passw0rd`, `Admin@123`, `welcome123`, `root`) were recovered quickly because they are predictable and appear in common password lists (Figure 3).
- **Hardest to crack:** The uncracked hash likely did not appear in the wordlist and may be longer, less common, or more complex.
- **Password strength factors:** Length, randomness, and avoidance of common words/patterns significantly increase resistance to wordlist-based recovery.

## Risk Assessment

- **Account takeover:** Weak passwords enable rapid compromise, even with basic wordlists.
- **Breach impact:** Recovered credentials can expose sensitive data and allow privilege escalation.
- **Credential reuse:** Users often reuse passwords; one cracked hash can lead to access across multiple systems.

## Recommendations

- Enforce **minimum length** (12–16+ characters) and encourage passphrases.
- Block common passwords and known breached password lists.
- Store passwords with **salted, slow hashes** (Argon2/bcrypt/scrypt) rather than fast hashes like MD5.
- Enable **MFA** and monitor for credential stuffing attempts.

## Conclusion

Most hashes were recovered using a small wordlist, demonstrating that common passwords are highly vulnerable. Stronger, unique passwords and modern hashing (salted and slow) are necessary to reduce cracking risk and limit the impact of credential compromise.
