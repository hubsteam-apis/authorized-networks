# Authorized Networks

This repository contains the list of IP addresses authorized to access resources across all Hubteam projects. This document provides a comprehensive explanation of what this list is, why it exists, and how it is used.

## What are Authorized Networks?

Authorized networks, in this context, refer to a list of specific IP addresses that have been pre-approved for access to our internal systems and services. This is a security measure known as an **IP whitelist** or **allowlist**. Only traffic originating from these approved IP addresses will be permitted to connect to our resources. Any connection attempt from an IP address not on this list will be automatically denied.

## Why Do We Use an IP Whitelist?

The primary reason for implementing an IP whitelist is to enhance the security of our infrastructure. By restricting access to a known and trusted set of IP addresses, we can significantly reduce the risk of unauthorized access and potential cyberattacks. This approach provides a strong first line of defense against malicious actors attempting to compromise our systems.

Key benefits of using an IP whitelist include:

- **Enhanced Security:** It drastically limits the attack surface by blocking all traffic from unknown sources.
- **Controlled Access:** It ensures that only authorized personnel and systems can interact with our sensitive resources.
- **Reduced Risk:** It helps prevent common attack vectors such as brute-force attacks, credential stuffing, and other automated threats.

## How is the List of Authorized Networks Maintained?

The list of authorized IP addresses is centrally managed and stored in a single JSON file within this repository. This centralized approach ensures consistency and simplifies the process of updating the list.

- **Storage:** The list is stored in the `networks.json` file in the root of this repository.
- **Format:** The `networks.json` file contains a simple JSON array of strings, where each string is an IP address.
- **Updates:** Any changes to the list of authorized networks must be made by updating the `networks.json` file and committing the changes to this repository. This ensures that all changes are version-controlled and auditable.

## How to Check if Your IP Address is Authorized

If you are experiencing authorization or access errors, the first step is to verify whether your current public IP address is included in the authorized networks list. You can do this by checking the contents of the `networks.json` file in this repository.

You can view the raw JSON file directly at the following URL:

[https://raw.githubusercontent.com/hubsteam-apis/authorized-networks/main/networks.json](https://raw.githubusercontent.com/hubsteam-apis/authorized-networks/main/networks.json)

## What to Do if Your IP Address is Not on the List

If your IP address is not on the list and you require access to our resources, you will need to request that your IP address be added. Please follow your organization's internal procedures for requesting access. This typically involves contacting your team lead or the IT department with a justification for why your IP address needs to be added to the whitelist.

**Note:** For security reasons, we do not accept pull requests or direct requests from the public to add IP addresses to this list. All requests must come through official internal channels.
