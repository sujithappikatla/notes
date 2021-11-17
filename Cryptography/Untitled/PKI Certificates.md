- Certificates in general should not be called SSL/TLS certificates. These are PKI certificates
- SSL/TLS Certificate is one type of PKI Certificate.
- PKI Certificates also called as X.509 Certificate(name came  from X.509 standard being used )
- PKI certifcates can be Issued to users, devices, applications
- Can be used for specific purposes like file encryption, securing network traffic using SSL, code signing. Type if purpose can be defined in Certificate Template
- Can be stored in files on devices, on smart cards, in firmware(TPM)

### What's in a PKI Certificate
- Version number (x.509 version)
- Serial number (used in making revocation list CRL)
- CA digital signature (used for verifying CA) and algorithm used
- Validity period
- Certificate usage details
- Subject name, URL, email address
- Public/Private Key

### Wildcard SSL/TLS Certificates
- can be used for multiple DNS second-level domains via the Subject Alternative Name (SAN) field
- certificate is issued to the top-level DNS domain
- Certificate issued to \*.fakecorp.com can be used for india.fakecorp.com and europe.fakecorp.com

### Certificate Revocation List
- published by CA
- Contains List of revoked certificate serial numbers
- Revocation reasons - lost or compromised device, employee termination.
- Apps using certificates should retrieve the CRL before using certificates

##### Online Certificate Status Protocol (OCSP)
- Consists of a client component and server-side responder component
- Allows querying of the status of specific certificates
- unlike CRL, the entire list does not have to be downloaded

##### OCSP Stapling
- Certificate Owner checks the CA for its status periodically, such as web server with an SSL/TLS certificate
- Clients connecting to the secured website receive OCSP status for that website
- Clients do not have to query the OCSP responder for website certificate status separately

##### Public Key Pinning (PKP)
- Through the HTTP header, trusting devices download a trusted copy of a servers certificate, which includes the public key (it is "pinned" locally)
- RFC 7469: "Key pinning is a trust-on-first-use (TOFU) mechanism"
- Upon future connections to the server, clients require that the server provide a fingerprint that has been previously pinned
- Mitigates certificates issued to know hosts from unauthorized CAs such as mail.google.com being issued a certificate from an attackers self-signed CA