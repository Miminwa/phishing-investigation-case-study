# Security and Disclosure Notes

This repository is a sanitized portfolio case study based on a real defensive investigation.

## What is intentionally excluded

The repository does not include:

- the original `.eml`
- the original PDF attachment
- recipient or employee addresses
- organization-specific mailbox information
- unique tracking tokens
- internal mail logs
- full live malicious URLs
- confidential company information

## Why

Raw phishing artifacts can contain personal data, internal identifiers, tracked links, and material that should not be redistributed publicly. The goal of this repository is to demonstrate the investigation method and reasoning without exposing the affected organization or creating unnecessary risk.

## Safe indicator notation

Suspicious domains are written in defanged form, for example:

`example[.]com`

This reduces accidental clicks while preserving analytical value.

## Scope of conclusions

The evidence supports a phishing assessment based on the deceptive PDF link, redirect behavior, unrelated and newly registered destination domain, and campaign context.

The final destination server was unavailable at the time of testing. Therefore, this repository does not claim to have observed the final credential-harvesting page, malware payload, or other post-redirect behavior.
