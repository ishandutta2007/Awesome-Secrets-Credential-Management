# Awesome Secrets & Credential Management Ecosystem 🔑🛡️

![Awesome Secrets & Credential Management Ecosystem Banner](assets/banner.svg)

<p align="center">
  <a href="https://github.com/ishandutta2007/Awesome-Awesome-Awesome"><img src="https://img.shields.io/badge/Awesome-%E2%9C%94-blueviolet?style=flat-square&logo=github" alt="Awesome"/></a><a href="https://discord.gg/jc4xtF58Ve"><img src="https://img.shields.io/badge/Discord-5865F2?stlle=for-the-badge&logo=discord&logoColor=white" alt="Discord" /></a>
  <a href="https://github.com/ishandutta2007/Awesome-Awesome-Awesome"><img src="https://awesome.re/badge.svg" alt="Awesome List"/></a>
  <a href="https://creativecommons.org/publicdomain/zero/1.0/"><img src="https://img.shields.io/badge/License-CC0_1.0-lightgrey.svg" alt="License: CC0-1.0"/></a>
  <a href="https://github.com/ishandutta2007"><img alt="GitHub followers" src="https://img.shields.io/github/followers/ishandutta2007?label=Follow" /></a>
</p>

> 🔐 A curated list of **Secrets Management**, **Credential Rotation**, **Vault Software**, **Privileged Access Management (PAM)**, and **Cloud Security** solutions for infrastructure, CI/CD, and application workloads.

This repository tracks notable commercial **SaaS secrets management platforms** and **open-source security tools** designed to securely store, rotate, distribute, and audit credentials — including API keys 🔑, database passwords 🔐, TLS certificates 📜, SSH keys 🗝️, and access tokens 🎫 — across modern hybrid cloud and GitOps environments.

---

## 📑 Table of Contents

- [📊 Market Size & Industry Dynamics](#-market-size--industry-dynamics)
- [☁️ SaaS / Commercial Products](#️-saas--commercial-products)
- [💻 Open-Source GitHub Projects](#-open-source-github-projects)
  - [🏛️ Core Secrets Stores & Vaults](#️-core-secrets-stores--vaults)
  - [📦 GitOps & File Encryption Tools](#-gitops--file-encryption-tools)
  - [☁️ Cloud-Native & Identity Infrastructure](#️-cloud-native--identity-infrastructure)
  - [🔑 Password Managers & Team Credentials](#-password-managers--team-credentials)
- [🏗️ Architectural Best Practices](#️-architectural-best-practices)
- [🤝 How to Contribute](#-how-to-contribute)
- [💖 Support & Sponsorship](#-support--sponsorship)
- [⭐ Star History](#-star-history)
- [⚠️ Disclaimer](#️-disclaimer)

---

## 📊 Market Size & Industry Dynamics

> 📈 **Estimated Market Size & Fragmentation**: The global Secrets Management market is estimated at **$4.22 Billion (2025)** and is projected to reach **$8.05 Billion by 2030** (CAGR ~13.8%). The sector is **moderately fragmented** — while cloud hyperscalers (AWS, Azure, GCP) and legacy enterprise leaders (Palo Alto / CyberArk, IBM / HashiCorp) hold major market share in enterprise workloads, fast-moving SaaS startups (Doppler, Infisical, Akeyless) and strong open-source ecosystems prevent a "winner-take-all" dynamic.

---

## ☁️ SaaS / Commercial Products

The table below lists leading commercial and cloud-native secrets management solutions, sorted by **Company Size / Valuation / Revenue** in descending order.

| Vendor / Product | Company Size / Valuation / Revenue | Pricing Model | Free Tier & Trial Limits | Key Features & Best Use Case |
| :--- | :--- | :--- | :--- | :--- |
| **[Azure Key Vault](https://azure.microsoft.com/en-us/products/key-vault)** | **$3.1 Trillion** (Microsoft Market Cap) | Pay-as-you-go (~$0.03 per 10k operations for Standard) | No permanent free tier (Included in $200 Azure free credit trial) | Hardware Security Module (HSM) option, Managed Identity integration. *Best for Azure-native workloads.* |
| **[Google Cloud Secret Manager](https://cloud.google.com/secret-manager)** | **$2.1 Trillion** (Alphabet Market Cap) | Pay-as-you-go ($0.06/secret/mo, $0.03 per 10k operations) | **Always Free Tier**: 6 active secret versions, 10,000 access operations/month | Workload Identity federation, automatic payload versioning. *Best for GCP-native workloads.* |
| **[AWS Secrets Manager](https://aws.amazon.com/secrets-manager/)** | **$2.0 Trillion** (Amazon Market Cap) | Pay-as-you-go ($0.40/secret/mo + $0.05 per 10k API calls) | **30-day free trial** (up to 30 secrets per account) | Built-in automatic rotation for Amazon RDS, Redshift, and DocumentDB. *Best for AWS-native workloads.* |
| **[CyberArk Conjur Enterprise](https://www.cyberark.com/)** | **$25 Billion** (Acquired by Palo Alto Networks; $1.36B Rev) | Enterprise Quote (per identity / workload / year) | **30-day Enterprise Trial** | Policy-as-code (YAML), mTLS Kubernetes authenticator, enterprise PAM integration. *Best for enterprise compliance.* |
| **[1Password Secrets Automation](https://www.1password.dev/secrets-automation)** | **$6.8 Billion** Valuation ($400M+ ARR) | $7.99/user/month (Business) + Connect usage | **14-day free trial** (Full Business/Enterprise plan) | Connect server, Service Account tokens, infrastructure secret isolation. *Best for teams using 1Password.* |
| **[HashiCorp Vault (HCP Cloud)](https://www.hashicorp.com/products/vault)** | **$6.4 Billion** (Acquired by IBM; $580M Rev) | Starts at **$0.03/hour** (~$22/month for Dev tier) | **$500 HCP Free Trial Credit** for new accounts | Managed HashiCorp Vault, dynamic database credentials, PKI engine, transit encryption. *Best for enterprise Vault without ops.* |
| **[Keeper Secrets Manager](https://www.keepersecurity.com/)** | **$225 Million+** ARR (~$60M Raised) | ~$15/user/month (Add-on to Keeper Enterprise) | **14-day free trial** (Full enterprise suite) | Zero-knowledge architecture, SOC 2 / ISO 27001 certified, BreachWatch integration. *Best for compliance-focused teams.* |
| **[Akeyless](https://www.akeyless.io/)** | **~$80 Million** Total Raised (Series B) | Consumption-based (custom per client/API call tier) | **Free Tier**: 5 clients, 500 static secrets, 5 dynamic/rotated secrets | Distributed Fragments Cryptography (DFC), zero-knowledge SaaS secrets vault. *Best for hybrid & multi-cloud security.* |
| **[Doppler](https://www.doppler.com/)** | **~$45 Million** Valuation ($44.5M Raised) | $8/user/month (Team tier) | **Free Developer Tier**: Up to 3 users, 10 projects, 3-day log retention | Developer-first SecretOps, zero-downtime dual-secret rotation, CLI & syncs. *Best for fast developer UX without self-hosting.* |
| **[Infisical (Cloud)](https://infisical.com/)** | **~$50M - $100M** Valuation ($18.9M Raised) | $18/identity/month (Pro tier) | **Free Tier**: 5 identities, 3 projects, 3 environments, 100+ integrations | Managed cloud for Infisical open-source platform, Access Requests, dynamic secrets. *Best for developer-centric secrets governance.* |

---

## 💻 Open-Source GitHub Projects

The open-source community provides some of the most resilient secrets management frameworks. Below, tools are categorized and sorted by **GitHub Stars_Count** in descending order. Each badge links directly to the repository's stargazers page.

### 🏛️ Core Secrets Stores & Vaults

| Repository | GitHub_Stars | License | Key Description |
| :--- | :--- | :--- | :--- |
| **[HashiCorp Vault](https://github.com/hashicorp/vault)** | [![Stars](https://img.shields.io/github/stars/hashicorp/vault?style=social&color=white)](https://github.com/hashicorp/vault/stargazers) | BSL-1.1 | **The reference implementation for secrets management.** Dynamic credentials, PKI, transit encryption, and extensive plugin ecosystem. |
| **[Infisical](https://github.com/Infisical/infisical)** | [![Stars](https://img.shields.io/github/stars/Infisical/infisical?style=social&color=white)](https://github.com/Infisical/infisical/stargazers) | MIT | **Modern developer-first secrets platform.** Features secret scanning, dynamic secrets, Access Requests, and end-to-end encryption. |
| **[OpenBao](https://github.com/openbao/openbao)** | [![Stars](https://img.shields.io/github/stars/openbao/openbao?style=social&color=white)](https://github.com/openbao/openbao/stargazers) | MPL-2.0 | **Linux Foundation community fork of HashiCorp Vault.** Fully open-governance alternative to BSL licensing with Vault API compatibility. |
| **[CyberArk Conjur OSS](https://github.com/cyberark/conjur)** | [![Stars](https://img.shields.io/github/stars/cyberark/conjur?style=social&color=white)](https://github.com/cyberark/conjur/stargazers) | Apache-2.0 | **Policy-as-code secrets management.** Declarative YAML policies, mTLS Kubernetes authenticator, and JWT-based CI/CD authentication. |

---

### 📦 GitOps & File Encryption Tools

| Repository | GitHub_Stars | License | Key Description |
| :--- | :--- | :--- | :--- |
| **[SOPS (getsops)](https://github.com/getsops/sops)** | [![Stars](https://img.shields.io/github/stars/getsops/sops?style=social&color=white)](https://github.com/getsops/sops/stargazers) | MPL-2.0 | **File-level secrets encryption.** Encrypts YAML/JSON values with KMS (AWS, GCP, Azure) or PGP/Age for GitOps workflows. |
| **[Sealed Secrets](https://github.com/bitnami-labs/sealed-secrets)** | [![Stars](https://img.shields.io/github/stars/bitnami-labs/sealed-secrets?style=social&color=white)](https://github.com/bitnami-labs/sealed-secrets/stargazers) | Apache-2.0 | **Asymmetric encryption for Kubernetes secrets.** Allows safe storage of encrypted secrets in public Git repositories. |
| **[gopass](https://github.com/gopasspw/gopass)** | [![Stars](https://img.shields.io/github/stars/gopasspw/gopass?style=social&color=white)](https://github.com/gopasspw/gopass/stargazers) | MIT | **Terminal password manager for teams.** Uses GPG/age encryption and Git sync for distributed credential management. |
| **[git-secret](https://github.com/sobolevn/git-secret)** | [![Stars](https://img.shields.io/github/stars/sobolevn/git-secret?style=social&color=white)](https://github.com/sobolevn/git-secret/stargazers) | MIT | **Bash CLI to encrypt sensitive files inside Git.** Encrypts file contents using GPG for specified committers. |
| **[Blackbox](https://github.com/StackExchange/blackbox)** | [![Stars](https://img.shields.io/github/stars/StackExchange/blackbox?style=social&color=white)](https://github.com/StackExchange/blackbox/stargazers) | MIT | **Stack Exchange tool for GPG file encryption.** Safely stores secret files in VCS repos with multi-recipient encryption. |

---

### ☁️ Cloud-Native & Identity Infrastructure

| Repository | GitHub_Stars | License | Key Description |
| :--- | :--- | :--- | :--- |
| **[AWS Vault](https://github.com/99designs/aws-vault)** | [![Stars](https://img.shields.io/github/stars/99designs/aws-vault?style=social&color=white)](https://github.com/99designs/aws-vault/stargazers) | MIT | **Secure AWS credential storage.** Stores keys in OS keystore (Keychain/KWallet) and generates temporary STS credentials. |
| **[External Secrets Operator](https://github.com/external-secrets/external-secrets)** | [![Stars](https://img.shields.io/github/stars/external-secrets/external-secrets?style=social&color=white)](https://github.com/external-secrets/external-secrets/stargazers) | Apache-2.0 | **Kubernetes secrets synchronizer.** Syncs secrets from AWS Secrets Manager, GCP Secret Manager, Vault, etc., into K8s Secrets. |
| **[SPIRE (SPIFFE)](https://github.com/spiffe/spire)** | [![Stars](https://img.shields.io/github/stars/spiffe/spire?style=social&color=white)](https://github.com/spiffe/spire/stargazers) | Apache-2.0 | **Workload identity provider.** Establishes cryptographic identity (SVIDs) across heterogeneous infrastructure for zero-trust access. |

---

### 🔑 Password Managers & Team Credentials

| Repository | GitHub_Stars | License | Key Description |
| :--- | :--- | :--- | :--- |
| **[Vaultwarden](https://github.com/dani-garcia/vaultwarden)** | [![Stars](https://img.shields.io/github/stars/dani-garcia/vaultwarden?style=social&color=white)](https://github.com/dani-garcia/vaultwarden/stargazers) | AGPL-3.0 | **Lightweight Bitwarden server written in Rust.** Ideal for self-hosting with minimal resource overhead. |
| **[KeePassXC](https://github.com/keepassxreboot/keepassxc)** | [![Stars](https://img.shields.io/github/stars/keepassxreboot/keepassxc?style=social&color=white)](https://github.com/keepassxreboot/keepassxc/stargazers) | GPL-2.0 / GPL-3.0 | **Cross-platform offline password manager.** Fully local, encrypted KDBX database store. |
| **[Bitwarden Server](https://github.com/bitwarden/server)** | [![Stars](https://img.shields.io/github/stars/bitwarden/server?style=social&color=white)](https://github.com/bitwarden/server/stargazers) | GPL-3.0 | **Official backend infrastructure for Bitwarden.** Open-source enterprise password management server. |
| **[Passbolt API](https://github.com/passbolt/passbolt_api)** | [![Stars](https://img.shields.io/github/stars/passbolt/passbolt_api?style=social&color=white)](https://github.com/passbolt/passbolt_api/stargazers) | AGPL-3.0 | **Open-source team password manager built for DevOps.** OpenPGP-based credential sharing and API integration. |
| **[LessPass](https://github.com/lesspass/lesspass)** | [![Stars](https://img.shields.io/github/stars/lesspass/lesspass?style=social&color=white)](https://github.com/lesspass/lesspass/stargazers) | GPL-3.0 | **Stateless password generator.** Computes unique passwords locally without sync or database storage. |
| **[Padloc](https://github.com/padloc/padloc)** | [![Stars](https://img.shields.io/github/stars/padloc/padloc?style=social&color=white)](https://github.com/padloc/padloc/stargazers) | GPL-3.0 | **Modern open-source encrypted password manager.** Simple UI for cross-platform team credential management. |
| **[Master Password (Lyndir)](https://github.com/Lyndir/MasterPassword)** | [![Stars](https://img.shields.io/github/stars/Lyndir/MasterPassword?style=social&color=white)](https://github.com/Lyndir/MasterPassword/stargazers) | GPL-3.0 | **Stateless password algorithm.** Generates deterministic site passwords on-demand using a master key. |

---

## 🏗️ Architectural Best Practices

1. ⚡ **Prefer Dynamic Secrets over Static Credentials**: Dynamic secrets mint short-lived, single-use database users or cloud STS tokens per application request. This removes static credentials that require manual rotation.
2. 🔒 **Implement GitOps-Native Secret Encryption**: Use tools like **SOPS** or **Sealed Secrets** to encrypt values before committing files into git repos. Never commit plain-text credentials.
3. 🛡️ **Decouple Identity from Secret Storage**: Use zero-trust workload identities (**SPIFFE/SPIRE** or Cloud Workload Identity) to authenticate microservices before granting vault read privileges.
4. ⚙️ **Standardize Secret Injection**: Standardize on Kubernetes operators like **External Secrets Operator** or sidecar injection to seamlessly pass environment secrets to application containers.

---

## 🤝 How to Contribute

1. 🍴 Fork this repository.
2. 📝 Add or update entries in `README.md` maintaining the existing tabular format and Stars_Badges.
3. 🎯 Ensure descriptions remain objective, technical, and accurate.
4. 🚀 Open a Pull Request with a clear summary of your additions.

---

## 💖 Support & Sponsorship

Thank you for exploring this secrets management resource! If you find this curated list helpful for your security operations or engineering workflows:

- ⭐ **Star this repository** to help others discover it.
- 🔀 **Fork & Share** it with your team and security community.
- ☕ **Sponsor / Buy Me a Coffee**: Support ongoing open-source maintenance via [GitHub Sponsors](https://github.com/sponsors/ishandutta2007).

---

## ⭐ Star History

[![Star History Chart](https://star-history.dera.page/svg?eepos=ishandutta2007/Awesome-Secrets-Credential-Management&type=date&legend=top-left)](https://star-history.dera.page/#ishandutta2007/Awesome-Secrets-Credential-Management&type=date&legend=top-left)

---

## ⚠️ Disclaimer

- This list is **community-curated** for educational and architectural evaluation purposes.
- SaaS platforms introduce third-party risk into your credential path; evaluate SOC 2 Type II and ISO 27001 compliance.
- Self-hosted vaults (HashiCorp Vault, OpenBao, Infisical) require operational hardening (unsealing protocols, HA clustering, backup retention).
- License notice: HashiCorp Vault is under BSL-1.1; verify organizational licensing compliance before adoption.
