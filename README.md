
# Networkwalks-W3-B083--password-cracking--

# PASSWORD CRACKING WITH JOHN THE RIPPER AND NETWORKWALKS TOOLS

**W3-PM1 | W3-PM2 | CYBERSECURITY | NETWORKWALKS**

Week 3 Lab — Password Cracking of Password-Protected PDF Files Using John the Ripper (JTR), Johnny GUI and Networkwalks Online Tools.

| Field | Details |
|---|---|
| **Pentester Name** | Krrish Pravin Mukadam |
| **Program / Batch** | B084 - Networkwalks |
| **Date** | 20 November 2026 |
| **Modules Completed** | W3-PM1 (Password Cracking with JTR) |
| | W3-PM2 (Password Cracking with Networkwalks Tools) |
| **Target File** | My Locked PDF2.pdf |
| **Permission Secured from Client?** | Yes — File provided for lab exercise |
| **Phases Covered** | Phase 1: Hash Extraction |
| | Phase 2: Password Cracking (Local Tool) |
| | Phase 3: Password Cracking (Online Tool) |

---

## 1. Liability Disclaimer

I have performed these activities only on the files provided for this lab exercise, for educational and research purposes.

Do not use these techniques to access files without proper authorization. The instructor, authors and Networkwalks are not responsible for unauthorized use of this knowledge. Every action you take is your own responsibility.

---

## 2. Project Overview

Password cracking is the process of recovering a password from a protected file by testing possible password combinations against its extracted hash.

This Week 3 practical focuses on two different approaches:

1. John the Ripper (JTR) with Johnny GUI — A locally installed password-cracking suite.
2. Networkwalks Online Tools — Browser-based hash extraction and password-cracking tools.

The practical demonstrates how weak passwords can be recovered and why strong passwords are important for protecting sensitive documents.

---

## 3. Lab Environment

| Component | Details |
|---|---|
| Operating System | Kali Linux / Windows 11 |
| Password Cracking Tool | John the Ripper |
| GUI Tool | Johnny |
| Online Platform | Networkwalks |
| Hash Format | PDF ($pdf$) |
| Target File | My Locked PDF2.pdf |
| Browser | Web Browser |

---

## 4. Tools Used

| Tool | Purpose |
|---|---|
| John the Ripper (JTR) | Command-line password-cracking tool |
| Johnny GUI | Graphical interface for John the Ripper |
| Networkwalks Hash Calculator | Extracts password hashes from locked PDF files |
| Networkwalks Password Cracker | Tests candidate passwords against extracted hashes |
| Kali Linux | Linux environment for cybersecurity testing |
| Windows 11 | Host operating system |
| Web Browser | Accessing Networkwalks online tools |

---

## 5. Module 1 – Password Cracking with John the Ripper (W3-PM1)

### 5.1 Task

Recover the password of the supplied password-protected PDF file using John the Ripper and Johnny GUI.

### 5.2 Installation and Verification

First, check whether John the Ripper is installed.

```bash
which john
```

Check the available build information:

```bash
john --list=build-info
```

If John the Ripper is not installed, install it using:

```bash
sudo apt update
sudo apt install john -y
```

**Note:** The command `john --version` may return an unknown option error on some builds. This does not necessarily indicate an installation problem.

### 5.3 Hash Extraction

The password-protected PDF file must first be converted into a hash format that John the Ripper can understand.

The extracted hash starts with `$pdf$`.

Steps:

1. Downloaded the password-protected PDF file.
2. Opened the Networkwalks Hash Calculator.
3. Uploaded the PDF file.
4. Extracted the PDF hash.
5. Copied the complete hash value.
6. Saved the hash in a text file for local testing.

**Screenshot – PDF Hash Extraction**

![PDF Hash Extraction](screenshots/03-pdf-hash-extraction.png)

### 5.4 Password Cracking Using Johnny

Steps:

1. Opened Johnny GUI.
2. Loaded the extracted PDF hash.
3. Started a new password-cracking attack.
4. Waited for the attack to complete.
5. Observed the recovered password in the result table.

**Screenshot – Johnny Password Cracking Result**

![Johnny JTR Result](screenshots/05-johnny-jtr-result.png)

**Recovered Password:** `password1`

### 5.5 Observation

Johnny successfully identified the password `password1` from the loaded PDF hash.

This demonstrates that weak or commonly used passwords can be recovered through password-cracking techniques.

---

## 6. Module 2 – Password Cracking with Networkwalks Tools (W3-PM2)

### 6.1 Task

Recover the password of the supplied PDF using Networkwalks Hash Calculator and Networkwalks Password Cracker.

Both tools are browser-based and do not require local software installation.

### 6.2 Hash Extraction Using Networkwalks

Tool: https://networkwalks.com/hash-calculator

Steps:

1. Opened the Networkwalks Hash Calculator.
2. Selected the password-protected PDF file.
3. Uploaded the PDF.
4. Extracted the hash value.
5. Verified that the extracted hash started with `$pdf$`.
6. Copied the complete hash.

**Screenshot – Networkwalks Hash Calculator**

![Networkwalks Hash Calculator](screenshots/03-pdf-hash-extraction.png)

### 6.3 Password Cracking Using Networkwalks

Tool: https://networkwalks.com/password-cracker

Steps:

1. Opened the Networkwalks Password Cracker.
2. Pasted the extracted PDF hash.
3. Started the password-cracking attack.
4. Waited for the tool to test candidate passwords.
5. Observed the successful password match.

**Screenshot – Password Cracking Successful**

![Networkwalks Password Cracker](screenshots/01-online-password-cracker.png)

**Result:**

- Total candidates: 100
- Candidates tried: 91
- Password matches: 1
- Recovered password: `password1`

### 6.4 PDF Verification

After recovering the password, the password was used to open the protected PDF file.

The lab displayed a successful flag-capture message.

**Screenshot – First Flag Captured**

![First Flag](screenshots/02-pdf-flag-1.png)

**Screenshot – Additional Persistence Flag**

![Persistence Flag](screenshots/04-pdf-persistence-flag.png)

The screenshots provide evidence of successful completion of the lab activities.

---

## 7. Comparison of Methods

| Aspect | JTR + Johnny (Local) | Networkwalks (Online) |
|---|---|---|
| Installation Required | Yes | No |
| Internet Required | No for local cracking | Yes |
| Platform | Windows / Linux | Any device with browser |
| Ease of Use | Moderate | Easy |
| Interface | CLI and GUI | Browser-based |
| Data Privacy | Hash can remain local | Hash uploaded to third-party service |
| Configuration | Requires setup | Guided workflow |

---

## 8. Evidence Collected

The following screenshots were collected during the practical.

| Screenshot | Description |
|---|---|
| 01-online-password-cracker.png | Successful online password cracking |
| 02-pdf-flag-1.png | First flag captured |
| 03-pdf-hash-extraction.png | PDF hash extraction |
| 04-pdf-persistence-flag.png | Additional persistence flag |
| 05-johnny-jtr-result.png | Johnny password-cracking result |

---

## 9. Key Takeaways

1. Password cracking involves testing candidate passwords against an extracted password hash.
2. John the Ripper provides a local password-auditing solution.
3. Johnny GUI makes John the Ripper easier to use through a graphical interface.
4. Networkwalks provides browser-based tools for PDF hash extraction and password testing.
5. Weak passwords can be recovered quickly if they are included in the tested candidate list.
6. Uploading hashes to online services introduces privacy risks.
7. Long, unique and unpredictable passwords provide better protection for sensitive documents.

---

## 10. Security Recommendations

- Use long and unique passwords for sensitive PDF documents.
- Avoid common dictionary words and predictable password patterns.
- Never reuse passwords across different accounts or documents.
- Keep sensitive files and extracted hashes secure.
- Prefer local password-auditing tools when handling confidential client data.
- Perform password testing only with proper authorization.

---

## 11. Conclusion

The Week 3 practical successfully demonstrated two approaches to password cracking using John the Ripper with Johnny GUI and Networkwalks Online Tools.

Both methods identified `password1` as the matching password in the supplied lab evidence.

The practical helped understand PDF hash extraction, password auditing, candidate-password testing and the security risks associated with weak passwords.

It also demonstrated the importance of strong passwords and responsible handling of sensitive files and hashes.

---

## 12. Repository Structure

```text
networkwalks-w3-B083-password-cracking/
│
├── README.md
│
└── screenshots/
    ├── 01-online-password-cracker.png
    ├── 02-pdf-flag-1.png
    ├── 03-pdf-hash-extraction.png
    ├── 04-pdf-persistence-flag.png
    └── 05-johnny-jtr-result.png
```

---

## 13. References

- John the Ripper: https://www.openwall.com/john/
- Johnny GUI: https://openwall.info/wiki/john/johnny
- Networkwalks Hash Calculator: https://networkwalks.com/hash-calculator
- Networkwalks Password Cracker: https://networkwalks.com/password-cracker

---

**NETWORKWALKS | WEEK 3 | CYBERSECURITY | PASSWORD CRACKING**
