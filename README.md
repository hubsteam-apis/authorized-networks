# Authorized Access Networks

This repository serves as the **Centralized Source of Truth** for network authorization across the entire **Hubteam** ecosystem. It maintains a rigorous list of pre-approved IP addresses permitted to interact with our internal services, APIs, and infrastructure components.

---

## 1. Concept and Purpose

In modern cloud infrastructure, security is paramount. We employ a **Zero Trust Architecture** principle where access is not granted by default. Instead, we utilize an **IP Allowlist** (historically known as a *whitelist*) to define the boundaries of our trusted network.

> **Definition:** An Authorized Network is a specific IP address or range that has been vetted and granted permission to bypass perimeter firewalls and security gateways.

### Why This is Essential
| Feature | Benefit |
| :--- | :--- |
| **Attack Surface Reduction** | By blocking all unknown IPs, we eliminate 99% of automated bot attacks and unauthorized scans. |
| **Identity Verification** | IP validation acts as an additional layer of identity, ensuring requests originate from known physical or cloud locations. |
| **Compliance & Auditing** | Maintaining a public list of authorized networks allows for transparent auditing of who *can* access the infrastructure. |

---

## 2. Technical Implementation

The authorization data is stored in a structured format to allow for automated consumption by firewalls, load balancers, and application-level middleware.

### Storage Architecture
- **Location:** The primary data resides in `networks.json` within the root directory.
- **Access Method:** Systems can fetch this list programmatically via the GitHub Raw API.
- **Format:** A standardized JSON array of strings representing IPv4 addresses.

> [!IMPORTANT]
> **Real-time Synchronization:** Our internal security agents periodically poll the [JSON source](https://raw.githubusercontent.com/hubsteam-apis/authorized-networks/main/networks.json) to update firewall rules dynamically across all regions.

---

## 3. How to Verify Your Access

If you are encountering **403 Forbidden** errors or **Connection Timed Out** messages when trying to reach Hubteam services, your current network may not be authorized.

1.  **Identify Your IP:** Visit a service like `ifconfig.me` or `icanhazip.com` to find your public IPv4 address.
2.  **Check the List:** Search for your IP address in the [networks.json](https://raw.githubusercontent.com/hubsteam-apis/authorized-networks/main/networks.json) file.
3.  **Validate Format:** Ensure your IP is listed exactly as it appears in your browser, without extra spaces or hidden characters.

---

## 4. Requesting Access & Support

If your IP address is **not** on the authorized list and you have a legitimate business or development need to access our resources, you must initiate a formal authorization request.

### Contacting Hubteam
We do **not** process access requests via GitHub Pull Requests or Issues for security and privacy reasons. Instead, please reach out directly to the **Hubteam Support & Infrastructure Team** through any of our official channels:

*   **Official Websites:** Access our support portals at our main domains.
*   **Telegram:** Contact our official support bot or community managers.
*   **WhatsApp:** Use our dedicated business lines for urgent infrastructure requests.
*   **Discord:** Open a support ticket in the `#infrastructure-access` channel within the Hubteam server.

> [!WARNING]
> **Verification Required:** Be prepared to provide a valid justification and proof of identity. Unauthorized or suspicious requests will be ignored and the originating IP may be permanently blacklisted.

---

## 5. Security Best Practices

- **Avoid Public Wi-Fi:** We strongly discourage adding public or unsecured network IPs to this list.
- **Use Static IPs:** If possible, request authorization for static IPs or VPN exit nodes rather than dynamic residential IPs.
- **Periodic Review:** Hubteam regularly purges inactive or suspicious IPs from this list to maintain a lean and secure perimeter.

---
*Last Updated: February 2026*
*Maintained by Hubteam Infrastructure Security*
