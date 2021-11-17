- has longer validity period than issued certificates (10 years vs 2 years)
- Issues, renews, revokes certificates
- Also publishes a certificate revocation list (CRL)
- CAs issue certificates to RAs, RAs issue entity certificates
- Compromised top-level CS means all subordinate certificates are compromised

### Chain of Trust

- If Top level CA is trusted then any certificate issued by that CA is also trusted.
- This trust of entity certificates is done by having a digital signature of root CA in entity certificate
- This digital certificate is made by CAs private key(which only CA knows and secure)
- Anyone can verify if digital signature belongs to particular valid CA by using CAs public key(which anyone can access)

-> Usually CAs should be kept hidden from outside network and RA issued by these CA should be used to generate entity certificates. This adds level of security. And if one RA compromised then only that RA and certificates it created will be added to CRL(Certificate Revocation List).

-> Whenever CAs issues certificates with its digital signature, which can be tested by using public key of that CA

#### Self Signed CA
- Can Create Self Signed CA for like inside organization
- By default these wont be trusted by browsers or any other tools.
- We can tell browsers and tools to trust this self-signed CA, thereby trusting all entity certificates created by this root CA