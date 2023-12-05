BUG_Author:
Kelsey Tian

Affected version:
node-Tor

Vendor:
https://github.com/Ayms/node-Tor

Software:
https://github.com/Ayms/node-Tor

Vulnerability File:
1. lib/src/abstract-tls.js, line 72
2. lib/build-relays_and_dirs.js, line 82
   lib/src/removed/peersm_bridge_and_browser.js, line 178
   lib/publish.js, line 85
   lib/publish.js, line 98
3. lib/src/circuits.js, line 156
   lib/src/circuits.js, line 710
   lib/src/circuits.js, line 729

Description:
1. using insecure asymmetric encryption algorithms
createCert() uses the RSA-512 algorithm to generate a self-signed certificate. The key length does not meet the security requirements. The generated self-signed certificate may be vulnerable to attacks, and the private key may be cracked or information leaked.
Therefore, in practical applications, it is highly recommended to use longer RSA key lengths, such as 2048 bits or longer, to provide a higher level of security. Using secure key lengths reduces the risk of private keys being compromised by attackers and provides more reliable authentication and communication security.

2. using insecure hash algorithms
Use the less secure hash algorithm SHA-1 for secure verification of the WebSocket handshake process. SHA-1 has been widely considered to be a less secure algorithm and is not recommended for continued use in security contexts, being vulnerable to exhaustive searches and brute force attacks.
Therefore, in practical applications, SHA-256 and more secure hashing algorithms should be used first.

3. using insecure Diffie-Hellman group
Relay expansion operations are performed in the Tor network using a Diffie-Hellman group with a key length of actually 1024. These key lengths have become shorter in modern cryptography and are no longer considered a secure option.
To provide greater security, longer Diffie-Hellman groups are recommended, such as 2048 bits or longer key lengths.
