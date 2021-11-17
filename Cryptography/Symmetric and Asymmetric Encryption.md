# Symmetric Encryption

- Used Single key to Encrypt/Decrypt data
- Problem is sharing this key securely over internet

| Algorithm | Maximum Key Size (Bits) |
|-----------|-------------------------|
|   AES               |256|
| RC4 | 2048 |
| 3DES | 168 |
| Blowfish | 448 |

#### Working of Symmetric Encryption
Step 1 - Using Symmetric Key, Encrypt data at server side
Step 2 - Using Same Symmetric Key, Decrypt data at client side and vice versa


# Asymmetric Encryption
- Uses two mathematically related keys - Public and Private Keys
- Used by PKI(Public key Infrastructure commonly called public key cryptography eventhough private key involved)

| Algorithm | Maximum Key Size (Bits) |
|-----------|-------------------------|
| RSA | 4096 |
| Diffie-Hellman (more of a key exchange algorithm than encryption algorithm) | N/A | |
| ElGamal | 2048 |
| ECC | 256 |

#### Working of Asymmetric Encryption
Step 1 - Encrypt data with public key of server(which anyone can have) at client side
Step 2 - Decrypt data with private key of server(which only server has) at server side.


## How These Encryption methods used in SSL/TLS?

**Step 1 - ** Client sends list of ciphers that it supports to server.
**Step 2 - ** Server picks one of cipher which is strong and supported by server. Server sends selected cipher along with PKI(which consists server public key and hostname) to client
**Step 3- ** Client generates symmetric key and encrypts that unique key with server sent public key and send to server
**Step 4 - ** Server decrypts client sent encrypted symmetric key with server private key(which only server knows)
**Step 5 - ** After this all of communication is encrypted/decrypted using this shared symmetric key, which only server and client knows.

