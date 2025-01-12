# CryptoTool 🔐

A secure and user-friendly command-line tool for file encryption and decryption, supporting both AES and RSA encryption methods.

## Features

- Supports two encryption methods:
  - AES (Advanced Encryption Standard) with password protection
  - RSA (public-key cryptography) with key pair generation
- File integrity verification using SHA-256 checksums
- Secure key derivation using PBKDF2
- Animated progress display
- Command-line interface with argument parsing
- Hybrid encryption for RSA (AES+RSA) to handle large files

![image](https://github.com/user-attachments/assets/c9e8f499-646c-4c7e-b4d9-03dd39369d12)

## Requirements

```
cryptography>=41.0.0
```

## Installation

1. Clone the repository:
```bash
git clone https://github.com/Reo-0x/CryptoTool.git
cd CryptoTool
```

## Usage

### AES Encryption
```bash
python cryptotool.py encrypt aes input_file.txt encrypted_file.bin --password your_password
```

### AES Decryption
```bash
python cryptotool.py decrypt aes encrypted_file.bin decrypted_file.txt --password your_password
```

### RSA Encryption
```bash
python cryptotool.py encrypt rsa input_file.txt encrypted_file.bin
```
Note: This will generate a private key file (`encrypted_file.bin.key`) needed for decryption.

### RSA Decryption
```bash
python cryptotool.py decrypt rsa encrypted_file.bin decrypted_file.txt --key-file encrypted_file.bin.key
```

## Security Features

- Secure key derivation using PBKDF2-HMAC-SHA256 with 100,000 iterations
- Random salt generation for each encryption
- File integrity verification using SHA-256 checksums
- RSA key size: 2048 bits
- Hybrid encryption for RSA (AES+RSA) to securely handle files of any size
- Secure padding (OAEP) for RSA encryption

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Author

Made by Reo-0x (https://github.com/Reo-0x)


## Security Notice

- Always keep your encryption passwords and private keys secure
- Use strong, unique passwords for AES encryption
- Never share your RSA private keys
- Backup your encryption keys and passwords securely - if lost, encrypted files cannot be recovered
