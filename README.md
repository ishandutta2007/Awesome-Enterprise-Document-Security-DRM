# Awesome-Enterprise-Document-Security-DRM

# Top Enterprise Document Security & DRM Ecosystem

**Curated List of SaaS Platforms & Open-Source GitHub Projects**  
*Focused on Persistent File Encryption, Cross-Boundary Rights Control & Self-Hosted DRM*  
**Last updated: March 2026**

This repository tracks notable **SaaS platforms** and **open-source projects** for **Enterprise Document Security & DRM**. These tools protect sensitive files after they leave your network—attaching persistent usage rights (view, edit, print, share) that travel with the document and can be revoked even after delivery, covering everything from ecosystem-native information protection to independent cross-company rights management and open-source encryption vaults.

**Examples** include Microsoft Purview, Seclore, Fasoo, Fortra (Vera), Virtru, Digify, and open-source alternatives like Vault-Zip and Alcifra (the category leaders).

**Open-source emphasis**: This section highlights every major active project for self-hosted document encryption, open-source rights management, and community-driven file vaults—ideal for organizations seeking data sovereignty and avoiding per-user enterprise licensing. The open-source landscape is genuinely thin for **full DRM/IRM** (persistent rights that survive forwarding), but functional for **encryption at rest and controlled distribution** via license-key-gated vaults.

Contributions welcome! Open an PR to add/update entries. Keep descriptions factual and link to official sites.

## Table of Contents
- [SaaS/Hosted Platforms](#saas-products)
- [Open-Source GitHub Projects](#open-source-github-projects)
- [How to Contribute](#how-to-contribute)
- [Disclaimer](#disclaimer)

## SaaS/Hosted Platforms

| Product | Description | Pricing (Starting) | Free Tier / Trial Limits |
|---------|-------------|-------------------|--------------------------|
| **[Microsoft Purview Information Protection](https://www.microsoft.com/en-us/security/business/information-protection/microsoft-purview-information-protection)** | **The default choice for Microsoft 365 estates.** Protects documents where they are born—sensitivity labels trigger encryption and rights automatically. **Purview Suite: $12.00/user/month** (annual commitment, requires M365 E3 or Office 365 E3 plus Enterprise Mobility + Security E3) . Ranks #1 for ecosystem-native rights in M365 environments . | Suite: **$12.00/user/month** (annual) | No free tier; requires M365 E3/E5 licensing |
| **[Seclore](https://www.seclore.com/)** | **The deepest independent cross-company IRM.** Ecosystem-neutral—works across Microsoft, Google, and mixed estates. **Browser-based no-plugin access** for external recipients (a major adoption differentiator). Automation hooks attach rights as files leave DLP, ECM, or ERP systems . **Revoke after delivery: Yes. Print/copy control: Yes. Screen-capture defense: Partial** . | Quote-only | No free trial per TrustRadius ; demo via sales |
| **[Fasoo Enterprise DRM](https://www.fasoo.com/)** | **DRM as the organization's default state.** Protect-at-creation automation, derivative-document control, and **notably strong screen-capture defense**—the best in the category . Proven at mega-scale with two decades of enterprise-wide deployments, especially in APAC. **Revoke after delivery: Yes. Print/copy control: Yes. Screen-capture defense: Yes** . | Quote-only | **Free trial** available per TrustRadius |
| **[Fortra (Vera)](https://www.fortra.com/)** | **Pioneer of the "follow-the-file" persistent encryption model.** Dynamic policy and **kill-switch revocation** wherever the file travels. Under Fortra, sits beside Titus/BoldonJames classification for a label-to-rights chain. **Revoke after delivery: Yes. Print/copy control: Yes. Screen-capture defense: Partial** . | Quote-only | No free tier; demo via sales |
| **[Virtru](https://www.virtru.com/)** | **Email-first control.** Best for organizations whose primary leak path is the inbox. Browser-based, no-plugin access for recipients . | Quote-only | No free tier; demo via sales |
| **[Digify](https://digify.com/)** | **Deal-room lane.** Positioned for secure document sharing in M&A, fundraising, and confidential transactions . | Quote-only | Free trial available |

## Open-Source GitHub Projects

| Project | Star Badge | Description |
|---------|------------|-------------|
| **[Vault-Zip](https://github.com/debeemedia/vault-zip)** | [![Stars](https://img.shields.io/github/stars/debeemedia/vault-zip?style=social&color=white)](https://github.com/debeemedia/vault-zip/stargazers) | **The most complete open-source encrypted file vault with license-based access control.** **AES-256-GCM envelope encryption** for files at rest, **direct S3/MinIO streaming**, and **encryption key versioning/rotation with boot-time checks**. **Distribution encryption**: downloaded bundles are re-encrypted with the user's License Key, creating a unique `.vault` file tied to their credentials. **License key never sent to server during decryption**—client-side decryption with authenticated failure on wrong key or tampered file. Memory-efficient streaming (constant ~200MB RSS regardless of file size). Docker Compose deployment. **Best for organizations wanting a self-hosted vault that encrypts files at rest and controls distribution via license keys**—not full DRM with print/copy restrictions, but a practical foundation for sensitive file exchange . |
| **[Alcifra](https://github.com/HebelConsulting/Alcifra)** | [![Stars](https://img.shields.io/github/stars/HebelConsulting/Alcifra?style=social&color=white)](https://github.com/HebelConsulting/Alcifra/stargazers) | **Sovereign document workspace with encryption to each person's own hardware key.** **Every installation lets people enrol a smartcard or security key—two per person—and seals to it what is meant only for them.** **Two paid encryption modules**: **Encryption Module** (encrypted delivery via public certificates—private keys never leave the card/device) and **Encryption Service** (encryption at rest with HSM-held installation key, per-object keys, and re-wrap rotation without rewriting documents) . **Open protocols**: IMAP for notes, CalDAV/CardDAV for calendars, WebDAV for files—works with standard clients. Helm chart production deployment. **Best for sovereign/regulated environments needing hardware-key-sealed document delivery and at-rest encryption** without a SaaS dependency . |

### Additional Strong Open-Source Options

| Project | Star Badge | Description |
|---------|------------|-------------|
| **[Readium LCP Server](https://github.com/readium/readium-lcp-server)** | — | **Open-source DRM server for EPUB/PDF using the Readium LCP standard.** Handles license distribution and encrypted publication storage (filesystem or S3). **LCP (Lightweight Content Protection)** is a DRM scheme for ebooks/publishing—not enterprise document DRM. **Best for publishers** needing open-standard ebook protection rather than corporate file security . |
| **[reedb](https://www.ruby-toolbox.com/projects/reedb)** | — | **Ruby encrypted document-database hybrid with per-user encryption, nested ciphers, groups/zones for selective sharing, and rights management/revocation.** FUSE support for filesystem nodes. **Best for Ruby developers** wanting an encrypted storage layer with built-in access control primitives . |

**Frameworks for building custom systems**: The open-source path to document security is **encryption + controlled distribution**, not full DRM. **Vault-Zip** provides AES-256-GCM encryption at rest with license-key-gated distribution via `.vault` files . **Alcifra** adds hardware-key sealing (smartcard/security key) for encrypted delivery and HSM-backed at-rest encryption . **Neither enforces print/copy restrictions or screen-capture blocking like Fasoo or Seclore**—they protect confidentiality during storage and transit, not usage after decryption.

## How to Contribute

1. Fork the repo.
2. Add/edit entries in `README.md` (follow existing format).
3. Include: name, link, 1–2 sentence description, and whether it's SaaS or open-source.
4. Submit PR with a short explanation.

Star the repo if you find it useful!

## Disclaimer

- This is a **community-curated** list — not exhaustive and not an endorsement.
- Document security and DRM platforms handle legally sensitive files and encryption keys; enforce strict key management (HSM where possible), audit logging, and compliance with applicable data protection regulations. **A compromised DRM key can expose every protected document.**
- **Open-source document DRM does not exist as a mature category.** The projects listed provide **encryption at rest and controlled distribution**—Vault-Zip uses license-key-gated `.vault` files , Alcifra seals delivery to hardware keys and encrypts at rest with HSM-backed keys . **Neither enforces persistent usage rights after decryption**—once a recipient decrypts a file, they can print, copy, or screenshot it. **Commercial DRM platforms are quote-only** except Microsoft Purview ($12.00/user/month) . **Fasoo is the only option with strong screen-capture defense** . **Seclore is the best independent cross-company IRM** with browser-based no-plugin access for external recipients . **Purview is the default for Microsoft 365 estates** but protects only where documents are born in M365 . **Validate whether you need persistent rights that survive forwarding (commercial DRM) or confidentiality during storage/transit (open-source encryption)** before committing.

---

**Made for security engineers, compliance officers, and organizations protecting sensitive documents.**  
Let's make enterprise document security more open, portable, and rights-aware.
