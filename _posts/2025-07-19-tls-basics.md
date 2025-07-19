---
layout: post
title: "TLS Basics: Everything You Need to Know"
description: "A technical guide to understanding TLS from the ground up"
date: 2025-07-19
categories: [security, tls, encryption, web]
---

# TLS Basics: Everything You Need to Know

## What Is TLS?

**TLS (Transport Layer Security)** is a cryptographic protocol used to provide secure communication over a computer network. It ensures that data transferred between two parties (typically a client and a server) is:

- **Confidential**: Only the intended recipient can read the data.
- **Authenticated**: You know who you're talking to.
- **Tamper-proof**: The data hasn't been altered in transit.

TLS is the successor to SSL (Secure Sockets Layer), and most modern systems use TLS 1.2 or TLS 1.3.

---

## Why TLS Matters

Without TLS, data such as passwords, credit card numbers, or personal information sent over the internet could be intercepted and read by attackers. TLS prevents this by encrypting the data and verifying the identity of the communicating parties.

---

## The Building Blocks of TLS

TLS is composed of several core components:

### 1. **Encryption**
This hides the content of messages using algorithms like AES (Advanced Encryption Standard), so that third parties cannot understand the communication.

### 2. **Authentication**
Authentication ensures that the parties are who they say they are, usually through **digital certificates** and **public key infrastructure (PKI)**.

### 3. **Integrity**
TLS uses **message authentication codes (MACs)** to ensure data hasn’t been tampered with.

---

## TLS Handshake: Step-by-Step

The TLS handshake is the process that sets up the secure connection. Let's go through it in **TLS 1.2**, then briefly touch on **TLS 1.3**, which simplifies some parts.

### Step 1: Client Hello
- The client (browser) sends a **ClientHello** message to the server.
- It includes:
  - TLS version
  - Supported cipher suites
  - Random number (client_random)
  - Session ID (optional)
  - Supported compression methods

### Step 2: Server Hello
- The server responds with a **ServerHello** message.
- It includes:
  - Selected TLS version and cipher suite
  - Another random number (server_random)
  - Server's digital certificate (X.509)
  - Optional: Session ID, parameters for key exchange

### Step 3: Certificate Validation
- The client validates the server's certificate by:
  - Verifying the certificate chain (up to a trusted root CA)
  - Ensuring the certificate hasn't expired or been revoked
  - Checking the domain name

### Step 4: Key Exchange
Depending on the cipher suite used, key exchange can happen using:
- **RSA** (now discouraged)
- **Diffie-Hellman** (DH or ECDH)
- **Ephemeral Diffie-Hellman** (DHE/ECDHE) for **forward secrecy**

### Step 5: Pre-Master Secret and Key Derivation
- The client and server compute a shared **pre-master secret**.
- They use the pre-master secret, along with the two random values (client_random and server_random), to derive:
  - Session keys for encryption
  - MAC keys for integrity

### Step 6: Finished Messages
- Both sides send a **Finished** message encrypted with the newly established session key.
- This confirms that all further communication will be encrypted.

---

## TLS 1.3: What's New?

TLS 1.3 simplifies the handshake:
- Removes support for outdated algorithms (e.g., RSA key exchange, static DH)
- Encrypts more of the handshake earlier
- Reduces the number of round trips:
  - A full handshake can be done in 1 round trip
  - Supports 0-RTT for resumed sessions (with caveats)

Key differences:
- No more MACs: uses AEAD (Authenticated Encryption with Associated Data)
- Key exchange is always ephemeral (forward secrecy by default)
- No support for renegotiation

---

## Cipher Suites

A cipher suite is a named set of algorithms used to:
1. Exchange keys
2. Encrypt data
3. Ensure data integrity

Example (TLS 1.2):
```

TLS\_ECDHE\_RSA\_WITH\_AES\_256\_GCM\_SHA384

```

Breakdown:
- **ECDHE**: Ephemeral Elliptic Curve Diffie-Hellman (key exchange)
- **RSA**: For authentication (server certificate)
- **AES_256_GCM**: Symmetric encryption algorithm
- **SHA384**: For MAC and PRF (pseudorandom function)

In **TLS 1.3**, cipher suites are simpler, e.g.:
```

TLS\_AES\_128\_GCM\_SHA256

```

---

## Certificates and PKI

### What Is a Certificate?

A **digital certificate** (e.g., an X.509 certificate) contains:
- A public key
- Information about the entity (domain name, organization, etc.)
- Issuer (CA)
- Signature from the CA

### Role of Certificate Authorities (CAs)

A **Certificate Authority** signs certificates to vouch for the identity of the subject. Browsers trust a list of CAs. If a certificate is signed by a trusted CA, it is accepted as valid.

---

## Forward Secrecy

**Forward Secrecy** ensures that even if the server’s private key is compromised later, past sessions remain secure. This is achieved by using **ephemeral key exchanges** (like ECDHE) which generate unique session keys per connection.

---

## Session Resumption

TLS supports **resuming sessions** to avoid full handshakes:
- **Session IDs** (older method)
- **Session Tickets** (TLS 1.2)
- **0-RTT Resumption** (TLS 1.3): Faster but vulnerable to replay attacks

---

## TLS in Action

### HTTPS

When you see `https://` in your browser, TLS is in use over HTTP.

### TLS in Email, VPN, and More

TLS isn't just for web traffic:
- **SMTP, IMAP, POP3** can use TLS (STARTTLS)
- **VPNs** like OpenVPN use TLS for key exchange
- **VoIP**, messaging apps, etc., also rely on TLS

---

## Common TLS Attacks and Defenses

| Attack               | Description                               | Defense                       |
| -------------------- | ----------------------------------------- | ----------------------------- |
| Downgrade Attack     | Forcing a connection to a weaker protocol | Disable SSLv2/3, use TLS 1.2+ |
| MITM                 | Intercepting communication                | Certificate validation, HSTS  |
| BEAST, CRIME, POODLE | Exploit old protocols                     | Disable SSL, use TLS 1.2+     |
| Certificate Forgery  | Fake certificates                         | Certificate pinning, CT logs  |

---

## Best Practices

- Use **TLS 1.3** or at least **TLS 1.2**
- Enforce **HTTPS** with **HSTS**
- Obtain certificates from trusted CAs (e.g., Let’s Encrypt)
- Regularly rotate certificates and keys
- Disable weak ciphers and protocols
- Implement **OCSP Stapling** and monitor for revocation

---

## Conclusion

TLS is foundational to modern internet security. From initial handshake to encrypted communication, understanding TLS helps developers, sysadmins, and security professionals ensure privacy and integrity across the web. As the protocol evolves, best practices must be kept up-to-date to stay protected.

---

## Further Reading

- [RFC 8446 – TLS 1.3 Specification](https://datatracker.ietf.org/doc/html/rfc8446)
- [Mozilla TLS Guidelines](https://infosec.mozilla.org/guidelines/web_security)
- [SSL Labs Server Test](https://www.ssllabs.com/ssltest/)
- [TLS Basics by Internet Society](https://www.internetsociety.org/deploy360/tls/basics/)

---
