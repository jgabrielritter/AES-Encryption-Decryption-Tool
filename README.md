# AES Encryption Tool

A secure file encryption application with graphical user interface that utilizes AES-256-GCM encryption.

## Features

- **Strong Encryption**: Implements AES-256 in GCM mode with authentication tags to ensure data integrity and confidentiality
- **User-Friendly Interface**: Easy-to-use GUI for encrypting and decrypting files
- **Flexible Authentication**: Choose between password-based or key-based encryption
- **Secure Key Derivation**: Uses PBKDF2 with 100,000 iterations for password-based encryption
- **Random Key Generation**: Option to generate cryptographically secure random keys

## Requirements

- Python 3.6 or higher
- Required Python packages:
  - cryptography
  - tkinter (usually included with Python)

## Installation

1. Clone or download this repository
2. Install required dependencies:

```
pip install cryptography
```

3. Run the application:

```
python aes_encryption_gui.py
```

## Usage

### Encrypting a File

1. Select the input file you want to encrypt using the "Browse" button
2. Choose an output location for the encrypted file (optional - defaults to input filename + ".encrypted")
3. Select an authentication method:
   - **Password**: Enter and confirm a strong password
   - **Base64 Key**: Enter a Base64-encoded 256-bit key or generate one with the "Generate Key" button
4. Click the "Encrypt" button
5. Wait for the confirmation message

### Decrypting a File

1. Select the encrypted file using the "Browse" button
2. Choose an output location for the decrypted file (optional - defaults to removing ".encrypted" extension)
3. Enter the same password or Base64 key that was used for encryption
4. Click the "Decrypt" button
5. Wait for the confirmation message

### Generating Keys

1. Click the "Generate Key" button
2. A secure 256-bit random key will be generated, displayed in the Base64 Key field, and copied to your clipboard
3. Save this key securely - it will be required to decrypt any files encrypted with it

## Security Notes

- **Password Strength**: Choose long, complex passwords for better security
- **Key Storage**: Store your encryption keys securely; if lost, encrypted files cannot be recovered
- **Salt & IV**: The application automatically handles cryptographic salt and initialization vectors
- **Authentication**: GCM mode provides authentication to detect if encrypted files have been tampered with

## Technical Implementation

- Uses AES-256-GCM (Galois/Counter Mode) for authenticated encryption
- Implements PBKDF2-HMAC-SHA256 with 100,000 iterations for secure key derivation
- Stores salt, IV, and authentication tag along with the ciphertext
- Verifies file integrity during decryption

## Limitations

- No built-in key management system
- Does not support folder/directory encryption
- Large files are loaded entirely into memory

## License

Public use License.

## Acknowledgements

This tool uses the Python cryptography library for all cryptographic operations.
