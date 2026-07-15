# SafeKeepIt — published keys & integrity manifest

Public keys and certificates for **secure@safekeep.it** (Sébastien Patrick Lambla).

## Layout
- `secure-safekeep.asc` — OpenPGP public key (Ed25519). Fingerprint
  `6E28 5780 F451 22E8 0CA2 B252 533F 02C3 2FC5 A1C8`.
- `.well-known/openpgpkey/…` — Web Key Directory, so `gpg --locate-keys secure@safekeep.it` just works.
- More keys and X.509 certificates may be added here over time.

## Integrity
- `SHA256SUMS` — SHA-256 of every published artifact.
- `SHA256SUMS.asc` — detached OpenPGP signature over `SHA256SUMS`, made with the key above.

Verify:

    gpg --locate-keys secure@safekeep.it      # or: gpg --import secure-safekeep.asc
    gpg --verify SHA256SUMS.asc SHA256SUMS
    sha256sum -c SHA256SUMS
