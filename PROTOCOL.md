SOVEREIGNTY IDENTITY STACK
LIVINGLEDGER | Type SSH-Ed25519 | 02

1. Mandate
Identity = hardware-bound cryptographic signature.
Verified by deterministic DNS pulse.

2. DNS Schema
_identity TXT:
status=[active|revoked]; alg=ssh-ed25519; fp=SHA256:[hash]; activated=[date]; prev=[fp]

Rules
- Order irrelevant; verifiers parse map.
- Precedence: DNS > IDENTITY.json.
- Rollback: prev must match last-seen fp. No version numbers; identity is the fingerprint.

3. Validation
Valid IFF:
1. status=active (no resolve = invalid)
2. DNS fp == Git commit fp
3. Ed25519 signature valid

4. Dependencies
- Registrar = physical trust root (loss = identity death)
- Time: Git timestamps advisory; DNS activated = logical root

Infrastructure > Platform.
