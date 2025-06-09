# EncryptedPython
# Python RSA Encrypted Messaging Lab

This project allows two users to communicate securely over a network using **RSA public-key encryption**. Messages are encrypted with the recipient's public key and decrypted with the recipient’s private key. Wireshark or other packet analysis tools can be used to verify that the content is unreadable in transit.

## What You'll Learn
- How to use RSA encryption in Python
- Basic socket programming
- Threading for real-time communication
- How to inspect encrypted network traffic with Wireshark

## Features
- Secure, encrypted chat using **RSA (1024-bit)**
- Public key exchange at runtime
- Bidirectional messaging with threading
- Local network communication between two peers

## How It Works
1. The host and client each generate an RSA key pair on startup.
2. They exchange public keys via socket after connection.
3. Messages are encrypted with the receiver's public key and decrypted with their private key.
4. All communication on the network appears encrypted (binary garble) when viewed in Wireshark.

## Dependencies
- Python 3.x
- [`rsa`](https://pypi.org/project/rsa/)

Install with:
- bash
- pip install rsa

File Structure
- Encoded.py         # Main script containing both server and client logic

Usage
1. Start the script
- Run the script on both machines or terminals: python Encoded.py

2. Choose mode (Ensure the IP address and port in the script match your local network setup.)
- Host: Enter 1
- Connect: Enter 2

3. Chat securely
- Type messages and see them encrypted over the network!

Wireshark Analysis
- Open Wireshark and filter using the port you defined (default: 9999): tcp.port == 9999
- You’ll see the encrypted traffic—unreadable without the private key.

Security Notes
- This is a demo and does not use a secure channel for key exchange.
- For real-world applications, use secure key negotiation protocols (e.g., Diffie-Hellman or TLS).



