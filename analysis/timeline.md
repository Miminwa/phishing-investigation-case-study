# Investigation Timeline

This timeline is intentionally sanitized and focuses on the defensive workflow rather than organization-specific timestamps or identities.

| Stage | Action | Outcome |
|---|---|---|
| 1 | Suspicious payment-remittance PDF reported | Investigation opened |
| 2 | Original email requested in raw `.eml` form | Full headers and MIME structure preserved |
| 3 | Email authentication reviewed | SPF, DKIM, and DMARC passed |
| 4 | Sender context reviewed | Authentication alone did not establish legitimacy |
| 5 | PDF inspected statically | Visible address and embedded hyperlink did not match |
| 6 | Embedded URL extracted | No local click required |
| 7 | URL submitted for remote analysis | Multiple redirects observed |
| 8 | Effective destination identified | Newly registered, unrelated domain with Citrix-themed path |
| 9 | Destination response reviewed | Cloudflare 521; origin unavailable |
| 10 | Recipient exposure confirmed | Recipient reported no link interaction; 2FA enabled |
| 11 | Containment/scoping recommended | Mail-log review for similar messages and targeted indicator blocking |

## Decision points

### Why the investigation did not stop at SPF/DKIM/DMARC

All three controls passed, but those results only established authenticated sending behavior. Attachment and URL analysis still showed deception.

### Why the link was not opened directly

The embedded URL could be analyzed through static extraction and remote scanning without exposing a normal user endpoint or immediately signaling direct interaction from the recipient environment.

### Why the final payload is not claimed

The destination server was unavailable at the time of analysis. The investigation therefore documents what was observed without speculating about the unavailable landing page.
