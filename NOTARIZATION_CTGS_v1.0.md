# CTGS — Notarization and Anchoring Log

This file records how the canonical CTGS v1.0 materials have been
cryptographically anchored for provenance and tamper-evidence.

The anchoring model is:

- Individual files (spec, implementation notes, licenses, README) are hashed
  and listed in `HASHES.md`.
- `HASHES.md` itself is hashed to produce a **manifest hash**.
- That manifest hash is what gets anchored to a public, append-only system
  (e.g., a blockchain or timestamping service).

Anyone can:

1. Verify file integrity against `HASHES.md`.
2. Verify `HASHES.md` against the manifest hash.
3. Verify the manifest hash against the public anchor.

---

## 1. Current manifest (CTGS v1.0)

- **Manifest file:** `HASHES.md`  
- **Manifest hash algorithm:** SHA-256  

- **Manifest hash (hex):**
```text
84C099FFBB2B5F39D2A6A7AA6C534895FC59
```

- **Manifest creation date:** 2025-12-01  
- **Canonical version covered:** CTGS v1.0  

---

## 2. Anchoring records

This section records each time the manifest hash is anchored to an external,
append-only system.

### 2.1 Anchor entry template

When you perform an actual anchor, add a new entry like this:

```text
Anchor ID:        <short label, e.g., "eth-mainnet-001" or "btc-ots-001">
Date (UTC):       <YYYY-MM-DD>
Manifest hash:    84C099FFBB2B5F39D2A6A7AA6C534895FC59

System:           <e.g., "Ethereum mainnet", "Bitcoin via OpenTimestamps", etc.>
Method:           <e.g., "hash stored in tx data", "timestamped document hash">

Reference:        <transaction hash / proof link / timestamp ID>

Notes:            <optional context, e.g., wallet used, fee level, batch info>
Status:           <e.g., "confirmed", "pending confirmation">
```

### 2.2 CTGS v1.0 — Anchors

*(Fill these in as you perform them.)*

```text
Anchor ID:        TBD
Date (UTC):       TBD
Manifest hash:    84C099FFBB2B5F39D2A6A7AA6C534895FC59

System:           TBD
Method:           TBD

Reference:        TBD
Notes:            First public anchor of CTGS v1.0 manifest.
Status:           pending

Anchor ID:        btc-ots-001
Date (UTC):       2025-12-01
Manifest hash:    84C099FFBB2B5F39D2A6A7AA6C534895FC59

System:           Bitcoin via OpenTimestamps (web interface)
Method:           Web stamp of HASHES.md (manifest file)

Reference:        HASHES.md.ots (OpenTimestamps proof file in repo)
Notes:            First Bitcoin anchor for CTGS v1.0 manifest.
Status:           complete

```

---

## 3. Suggested anchoring approaches (non-normative)

The standard does not require a specific chain or service, but the following
patterns are typical:

1. **Public blockchain transaction (e.g., Bitcoin, Ethereum)**  
   - Include the manifest hash in the transaction data (OP_RETURN, memo, or data field).  
   - Record the transaction ID in this file under an anchor entry.

2. **Timestamping service**  
   - Use a reputable timestamping service that accepts a file or hash and issues a
     verifiable proof.  
   - Save the proof and reference/ID here.

3. **Multiple anchors over time (recommended)**  
   - Optionally, re-anchor the same manifest hash across different systems or
     at different times, especially when new versions are released or when
     regulatory milestones occur.

This log is meant to be **human-readable and checkable** by auditors, regulators,
and independent researchers.
