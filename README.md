# File Encryption Using GPG (Kali Linux)

## 📌 Project Overview
This project demonstrates how **GNU Privacy Guard (GPG)** can be used to securely encrypt and decrypt files using asymmetric cryptography.

The lab simulates a real-world scenario where a sensitive report must be protected before being shared. Only the intended recipient, who possesses the correct private key and passphrase, can decrypt and read the file.

This exercise was completed in a controlled, ethical lab environment.

---

## 🛠️ Tools & Technologies
- Kali Linux
- GPG (GNU Privacy Guard)
- Nano Text Editor
- Linux Terminal
- Oracle VirtualBox

---

## 📚 Key Concepts

### Asymmetric Encryption
Asymmetric encryption uses two keys:
- **Public Key:** Used to encrypt data
- **Private Key:** Used to decrypt data

Only the owner of the private key can decrypt files encrypted with the corresponding public key.

---

## ⚙️ Lab Procedure

### Step 1: Generate a GPG Key Pair
```bash
gpg --full-generate-key
```
An RSA 4096-bit key pair was generated with a passphrase to protect the private key.

---

### Step 2: Create a Confidential File
```bash
nano report.txt
```
A secret message was written and saved in the file.

---

### Step 3: Encrypt the File
```bash
gpg --encrypt --recipient user@demo.com report.txt
```
This creates an encrypted file named `report.txt.gpg`.

---

### Step 4: Verify Encryption
```bash
cat report.txt.gpg
```
The output appears as unreadable binary data, confirming successful encryption.

---

### Step 5: Simulate Secure Transfer
The original plaintext file was removed:
```bash
rm report.txt
```
Only the encrypted file remains.

---

### Step 6: Decrypt the File
```bash
gpg --decrypt report.txt.gpg > report.txt
```
The correct private key and passphrase are required to restore the original message.

---

## 📤 Sending an Encrypted File to Someone (Concept)
To securely send an encrypted file to another person:

1. The recipient generates their own GPG key pair.
2. The recipient shares **only their public key**.
3. The sender imports the public key and encrypts the file using it.
4. The encrypted file is sent.
5. Only the recipient can decrypt it using their private key.

This ensures confidentiality even if the file is intercepted.

---

## 📷 Screenshots
All screenshots demonstrating the lab steps are available in the `/screenshots` directory.

---

## 🔗 LinkedIn Post
This project is also documented with step-by-step screenshots on LinkedIn:

👉 **LinkedIn Post:**  
https://www.linkedin.com/feed/update/urn:li:ugcPost:7423028667448127489/

---

## 🎯 Learning Outcomes
- Learned how GPG implements public-key encryption.
- Generated and managed cryptographic keys.
- Encrypted and decrypted sensitive files securely.
- Understood secure file sharing using public keys.

---

## ⚠️ Ethical Disclaimer
This project is for educational purposes only.  
Do not encrypt or decrypt files without proper authorization.

---

## 👩‍💻 Author
**Bushra Saleem**  
Cybersecurity Learner | Aspiring SOC Analyst  
Karachi, Pakistan
