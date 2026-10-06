# Awesome-Secrets-Credential-Management

# Top Secrets & Credential Management Ecosystem

**Curated List of SaaS Products & Open-Source GitHub Projects**  
*Focused on Secret Stores, Credential Rotation & Self-Hosted Vaults*  
**Last updated: October 2026**

This repository tracks notable **commercial secrets management platforms** and **open-source projects** that securely store, rotate, and distribute credentials — API keys, database passwords, certificates, and tokens — across applications, CI/CD pipelines, and cloud infrastructure.

**Examples** include AWS Secrets Manager, HashiCorp Vault, Doppler, 1Password Secrets Automation, CyberArk Conjur, Akeyless, Infisical, Azure Key Vault, Google Cloud Secret Manager, and Keeper Secrets Manager (the category leaders).

**Open-source emphasis**: Secrets management is one of the strongest open-source security domains. **HashiCorp Vault** leads as the reference implementation, **Infisical** emerges as the modern developer-first alternative, **SOPS** and **Sealed Secrets** enable GitOps-native encryption, and **CyberArk Conjur OSS** brings policy-as-code. **OpenBao** provides the Linux Foundation fork of Vault. **gopass**, **Blackbox**, and **git-secret** handle Git-based secret management. This section is heavily expanded.

Contributions welcome! Open a PR to add/update entries. Keep descriptions factual and link to official sites.

## Table of Contents
- [SaaS/Hosted Platforms](#saas-hosted-platforms)
- [Open-Source GitHub Projects](#open-source-github-projects)
- [How to Contribute](#how-to-contribute)
- [Disclaimer](#disclaimer)

## SaaS/Hosted Platforms

- **[HashiCorp Vault (HCP)](https://www.hashicorp.com/products/vault)**  
  **Managed HashiCorp Vault** — the full Vault feature set without running the cluster . Dynamic secrets, PKI, transit encryption, and extensive plugin ecosystem . **The reference implementation for secrets management** . **Best for enterprises wanting Vault without operational burden** .

- **[AWS Secrets Manager](https://aws.amazon.com/secrets-manager/)**  
  **AWS's native secrets store** — native automatic rotation for RDS, Redshift, and DocumentDB . Tight IAM integration, Lambda/ECS/EKS support, and cross-region replication . **Best for AWS-native workloads** .

- **[Doppler](https://www.doppler.com/)**  
  **Proprietary SaaS secrets manager** — best-in-class developer experience and broad turnkey integrations . Rotated Secrets keeps two credentials alive for zero-downtime rotation . **No self-hosted option** . **Best for teams wanting zero operational overhead** .

- **[1Password Secrets Automation](https://www.1password.dev/secrets-automation)**  
  **Extends 1Password's vault to infrastructure secrets** — Service Accounts (CLI) or Connect servers (self-hosted, unlimited re-requests) . **Best for 1Password users** .

- **[CyberArk Conjur Enterprise](https://www.cyberark.com/)**  
  **Enterprise secrets management** — policy-as-code (YAML) with strong Kubernetes authenticator using mutual TLS . **Best for enterprises with PAM requirements** .

- **[Akeyless](https://www.akeyless.io/)**  
  **SaaS-based platform using Distributed Fragments Cryptography (DFC)** — zero-knowledge architecture . Centralized credential management, dynamic secrets, and automatic rotation . **Best for hybrid and multi-cloud environments** .

- **[Infisical (Cloud)](https://infisical.com/)**  
  **Managed cloud option for the open-source Infisical platform** — developer-first with clean CLI, native SDKs, secret scanning, and dynamic secrets . **Self-hosting available** . **Best for developers wanting modern secrets management** .

- **[Azure Key Vault](https://azure.microsoft.com/en-us/products/key-vault)**  
  **Azure's native secrets, keys, and certificates service** — Managed Identity integration and HSM-backed keys . **Best for Azure-native workloads** .

- **[Google Cloud Secret Manager](https://cloud.google.com/secret-manager)**  
  **GCP's native secrets store** — automatic versioning and access logs . Deep integration with GCP Workload Identity . **Best for GCP-native workloads** .

- **[Keeper Secrets Manager](https://www.keepersecurity.com/)**  
  **Zero-knowledge enterprise secrets management** — SOC 2 and ISO 27001 certified with BreachWatch . **Best for compliance-focused enterprises** .

## Open-Source GitHub Projects

### Core Secrets Management

- **[HashiCorp Vault](https://github.com/hashicorp/vault)**  
  **The most capable general-purpose secrets manager**, BSL licensed with **35,800+ GitHub stars** . **Dynamic secrets (mint unique database users per request), PKI, transit encryption, and massive plugin ecosystem** . **The reference implementation for the category** . **Trade-off**: Running Vault reliably (unsealing, HA, upgrades) is a real operational job . **Best for maximum capability and enterprise-grade secrets management** .

- **[OpenBao](https://github.com/openbao/openbao)**  
  **Linux Foundation fork of HashiCorp Vault**, MPL-2.0 licensed . **Community-driven under open governance** — no BSL licensing concerns . **API-compatible with Vault** . **Best for organizations wanting Vault without BSL** .

- **[Infisical](https://github.com/Infisical/infisical)**  
  **The leading modern open-source secrets platform**, MIT licensed with **27,400+ GitHub stars** . **Self-hostable with no artificial usage caps** in the free edition . Features **dynamic secrets, secret scanning, PKI/SSH management, and Access Requests** (multi-step approval chains with auto-expiring grants) . **Developer-first CLI and SDKs** . **The de facto open-source alternative to Doppler and Vault** for modern teams . **Best for developers wanting modern UX with self-hosting** .

- **[CyberArk Conjur Open Source](https://github.com/cyberark/conjur)**  
  **Open-source edition of Conjur**, Apache-2.0 licensed . **Policy-as-code YAML DSL** — roles, resources, and permissions are declarative . **Kubernetes authenticator (mTLS, no pre-shared secrets)** and **JWT auth for CI/CD** . **Best for Kubernetes-native secrets management** .

### GitOps & Encrypted Secrets

- **[SOPS (Mozilla)](https://github.com/mozilla/sops)**  
  **Secrets encryption tool that encrypts individual values within YAML/JSON files**, MPL-2.0 licensed . **Integrates with AWS KMS, GCP KMS, Azure Key Vault, and PGP** . **The standard for encrypting secrets in Git repositories** — version-controllable and diff-friendly . **Best for GitOps-native secret encryption** .

- **[Sealed Secrets (Bitnami)](https://github.com/bitnami-labs/sealed-secrets)**  
  **Kubernetes-specific secret encryption for GitOps**, Apache-2.0 licensed . **Encrypts secrets into SealedSecret resources** that can be stored in public version control and decrypted only within the cluster . **Best for Kubernetes GitOps** .

- **[External Secrets Operator](https://github.com/external-secrets/external-secrets)**  
  **Kubernetes operator that syncs secrets from external providers**, Apache-2.0 licensed . **Integrates Vault, AWS Secrets Manager, GCP Secret Manager, and more into Kubernetes Secrets** . **Best for Kubernetes secret synchronization** .

- **[gopass](https://github.com/gopasspw/gopass)**  
  **Terminal-based password manager using GPG or age encryption with Git synchronization**, MIT licensed . **Treats version control repositories as the primary storage backend** . **Best for team secret sharing with version history** .

- **[Blackbox (StackExchange)](https://github.com/StackExchange/blackbox)**  
  **GPG-based secret management for version control systems**, MIT licensed . **Encrypts files for safe storage at rest** . **Best for multi-recipient encryption** .

- **[git-secret](https://github.com/sobolevn/git-secret)**  
  **Bash-based CLI tool for managing sensitive files within Git repositories**, MIT licensed . **Encrypts files directly in the repo** . **Best for simple Git secret management** .

### Cloud-Native & Specialized

- **[aws-vault (99designs)](https://github.com/99designs/aws-vault)**  
  **Secure credential manager for AWS**, MIT licensed . **Stores long-term keys in OS keystore and exchanges for short-lived temporary sessions** . **Supports MFA and AWS Identity Center SSO** . **Best for AWS credential security** .

- **[SPIFFE and SPIRE](https://github.com/spiffe/spire)**  
  **Standards and implementation for cryptographic workload identity**, Apache-2.0 licensed . **Provides identity foundation for secrets management in zero-trust architectures** . **Best for workload identity** .

- **[Infisical Agent](https://github.com/Infisical/infisical)** — Already listed. **Sidecar agent for secret injection** .

- **[Vault Secrets Operator](https://github.com/hashicorp/vault-secrets-operator)** — Kubernetes operator for Vault .

### Additional Strong Open-Source Options

- **Passbolt** — Open-source password manager for teams .
- **KeePassXC** — Offline password manager .
- **Bitwarden** — Open-source password manager with self-hosted option .
- **Vaultwarden** — Lightweight Bitwarden server in Rust .
- **Padloc** — Open-source password manager .
- **LessPass** — Stateless password manager .
- **Spectre** — Stateless password manager .
- **Master Password** — Stateless password manager .

**Frameworks for building custom secrets management solutions**: Choose based on deployment requirements and operational capacity. **HashiCorp Vault** for maximum capability with dynamic secrets and PKI — accept the operational burden . **Infisical** for Vault-style dynamic secrets and Access Requests without the ops weight . **OpenBao** for Vault-compatible with open governance . **SOPS + Sealed Secrets** for GitOps-native secret encryption . **Conjur Open Source** for policy-as-code and Kubernetes identity integration . **External Secrets Operator** for Kubernetes secret synchronization . For cloud-native workloads, native services (AWS Secrets Manager, Azure Key Vault, GCP Secret Manager) integrate most cleanly with their respective IAM — **but standardize on one** rather than fragmenting across three . The most secure architectural pattern: use **dynamic secrets** wherever possible (unique credential per request, short-lived) rather than static secrets that must be rotated .

## How to Contribute

1. Fork the repo.
2. Add/edit entries in `README.md` (follow existing format).
3. Include: name, link, 1–2 sentence description, and whether it's SaaS or open-source.
4. Submit PR with a short explanation.

Star the repo if you find it useful!

## Disclaimer

- This is a **community-curated** list — not exhaustive and not an endorsement.
- Secrets management tools store credentials that provide access to critical systems. Self-hosted solutions require proper security hardening, backup procedures, and unsealing/HA configuration for production use.
- **SaaS secrets managers introduce a third party into your secret distribution path** — trust and availability of that provider become part of your threat model . Evaluate compliance posture (SOC 2, ISO 27001) before adoption.
- **License considerations**: HashiCorp Vault uses BSL (not OSI), OpenBao uses MPL-2.0, Infisical uses MIT, and Conjur uses Apache-2.0. Verify licensing against your use case before committing .
- **Dynamic secrets are more secure than static secrets** — Vault and Infisical mint unique credentials per request, eliminating long-lived secrets that must be rotated. Prefer dynamic over static whenever possible .
- The open-source ecosystem provides strong secret storage, rotation, and encryption foundations, but **enterprise support, compliance certifications, and managed SLAs** remain primarily commercial offerings.

---

**Made for security engineers, platform teams, and organizations seeking secrets management sovereignty.**  
Let's make secrets and credential management more open, transparent, and secure.
