# Certificate Lifecycle

1. Certificate Request
2. Certificate Issuance
3. Certificate Usage
4. Certificate Revocation
5. Certificate Renewal
6. Certificate Expiry

## Certificate Request
- A public and private key pair is generated first
- private keys can be copied or made available to thrusted third parties(key escrow)
- CSR is generated next, which includes a unique public key, commonly in PKCS#10 format (public key cryptography standards - PKCS)
- CSR is sent to a certificate authority for signing

### Certificate signing request
- Local Information needed
- Subject  Common Name, such as www.google.com
- Email address

## Certificate Issuance
- After checking organization details, certificate is issued to that organization.
- This process can be manual or automated.

## Certificate Usage
- Defined in the certificate details
- Email encryption and signing
- File system Encryption
- Code signing
- Apps can first verify the validity of a certificate before using them (CRL and OSCP)

## Certificate Revocation
- Certificate compromise
- Employee leaving organization
- Certificate serial number for revoked certificates can be acquired via the CRL or the OCSP

## Certificate Renewal
- Certificate expiry is a security mechanism
- Time frame varies depending on issuer; the norm is two years
- Manual or automated (automation such as through SCEP(Simple Certificate Enrollment Protocol))
- Public CAs notify subscribers via email
- Renewal must occur before certificate expiration

## Certificate Expiry
- The norm is a 90 day notification prior to expiry
- websites with expired SSL/TLS certificates: user web browsers no longer trust the site