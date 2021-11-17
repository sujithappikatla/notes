- Collection or Hierarchy of digital Security Certificates.
- Certificates always contain public keys in them.
- Certificates may or may not conatin private keys.
- Private keys can also be stored in seperate file

# PKI Components
| | |
|------------|----------|
| Certificate Authority (CA) | Issues, renews, revokes certificates |
| Registration Authority (RA) | Subordinate CA, should be used to manage certificates | 
| Certificate Revocation List (CRL) | Conatains all compromised/revoked certificate serial numbers |
| Certificate Template | Blueprint used when creating certificates |
| Certificate | Contains subject name, signature of CA, expiry information, public/private key |


### Single Tier PKI
CA -> Manages Certificates for users, devices, applications

### Multi-Tier PKI
CA -> RA -> Manages Certificates for users, devices, applications