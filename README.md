# BitScholars Protocol

## Next-Generation Academic Verification Protocol on Bitcoin Layer 2

---

## 📖 Overview

**BitScholars** is a decentralized academic verification protocol built on the **Stacks Layer 2** framework, secured by Bitcoin’s proof-of-work consensus. It transforms fragile paper-based diplomas into **sovereign, tamper-proof digital credentials** that are **permanently anchored to Bitcoin**.

The protocol enables universities, colleges, and academic institutions worldwide to issue **cryptographically verifiable credentials** that can be instantly validated by employers, governments, and organizations—transcending borders, languages, and institutional silos.

---

## 🎯 Key Features

* **Institutional Onboarding** – Stake-based institution registration with governance protections.
* **Immutable Credentials** – Academic records stored on-chain, ensuring durability and authenticity.
* **Cross-Institutional Endorsements** – Peer-to-peer validation network to strengthen trust.
* **Delegated Authority** – Institutions can assign role-based delegates with time-bound permissions.
* **Ownership Transfers** – Secure, time-locked credential ownership transfers between principals.
* **AI-Resistant Verification** – Cryptographic proof prevents forgery or synthetic document fraud.
* **Global Interoperability** – Universal standard for academic verification across borders.

---

## 🏗 System Overview

The BitScholars Protocol consists of four main layers:

1. **Institution Layer**

   * Registry of authorized academic institutions.
   * Stake-based admission mechanism.
   * Reputation system based on endorsements and issued credentials.

2. **Credential Layer**

   * Immutable mapping of credentials (student ↔ institution ↔ metadata).
   * Supports categories (degree, certificate, diploma).
   * Includes expiry, revocation, and validation scoring.

3. **Endorsement Layer**

   * Enables institutions to **endorse** credentials from peers.
   * Weight-based reputation impact.
   * Anti-duplication safeguards for trust integrity.

4. **Delegation & Transfer Layer**

   * Institutions can grant temporary authority to delegates.
   * Students can request ownership transfers (e.g., migration of records across wallets).

---

## ⚙️ Contract Architecture

The protocol is implemented in **Clarity** with the following components:

### Constants & Errors

* `MINIMUM-STAKE` – stake required for onboarding institutions.
* Rich set of error codes for authorization, validation, and operational failures.

### Data Structures

* **Institutions Map** – Registry of active academic institutions.
* **Credentials Map** – On-chain academic record ledger.
* **Endorsements Map** – Cross-institutional trust and validation system.
* **Delegates Map** – Institutional delegation framework.
* **Transfer Requests Map** – Time-bound secure credential transfers.

### Core Functions

* `register-institution` – Onboard a new institution with STX stake.
* `issue-credential` / `batch-issue-credentials` – Issue verifiable academic records.
* `endorse-credential-extended` – Provide institutional trust signaling.
* `add-delegate` – Grant delegation with scope and expiry.
* `request-credential-transfer` – Transfer credential ownership securely.

### Query Functions

* `get-institution-info` – Retrieve institution profile.
* `get-credential-info` – Fetch credential metadata and verification state.
* `get-endorsement-info` – Inspect credential endorsements.
* `get-delegate-info` – View delegate permissions.
* `is-credential-valid` – Verify real-time credential validity.
* `get-validation-level` – Query validation trust score.

---

## 🔄 Data Flow (Credential Lifecycle)

1. **Institution Registration**

   * Institution stakes STX and is recorded in `institutions`.

2. **Credential Issuance**

   * Institution issues a credential → added to `credentials` map.

3. **Endorsements**

   * Other institutions endorse the credential → stored in `endorsements`.
   * Endorsement weight improves trust score.

4. **Verification**

   * Employers or third parties call `is-credential-valid`.
   * Verification includes expiry, revocation, and endorsement score.

5. **Ownership Transfer (Optional)**

   * Student initiates transfer request → added to `transfer-requests`.
   * Credential moves securely to a new wallet.

---

## 🔐 Security Considerations

* **Immutable Credentials** – Once issued, credentials cannot be altered.
* **Expiry & Revocation** – Supports time-bound or revoked records.
* **Delegation Safeguards** – Prevents self-delegation and enforces expiry.
* **Validation Rules** – Strict input checks for strings, years, permissions, and comments.
* **Endorsement Integrity** – Prevents duplicate endorsements and weight abuse.

---

## 🌍 Use Cases

* **Universities** issuing tamper-proof diplomas.
* **Employers** instantly verifying applicant credentials.
* **Governments** authenticating foreign certificates for migration/visa applications.
* **Students** owning their credentials across wallets, job markets, and borders.

---

## 📌 Future Extensions

* DAO-based governance for institutions.
* Cross-chain interoperability with DID standards.
* Decentralized reputation scoring for institutions.
* Privacy-preserving verifications (zero-knowledge proofs).

---

## 📝 License

This protocol is open-source and available under the **MIT License**.
