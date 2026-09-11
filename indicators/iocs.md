# Indicators of Compromise / Investigation Indicators

The public repository intentionally contains only sanitized or defanged indicators.

## Network indicator

```text
secure[.]businessresourcecollaboration[.]com
businessresourcecollaboration[.]com
```

Observed path:

```text
/citrix-receiver/Windows/
```

## Behavioral indicators

- Payment/remittance-themed lure
- PDF attachment used as the delivery mechanism
- Visible hyperlink text did not match the actual embedded URL
- Redirect chain passed through legitimate tracking infrastructure
- Final destination was unrelated to the payment context
- Destination domain was recently registered at the time of analysis
- Citrix-themed URL path
- Final origin server returned Cloudflare 521 during analysis

## Email indicators intentionally omitted

The following are retained only in the private/internal case record and are not published here:

- recipient address
- organization name
- exact sender address
- sender-specific identifiers
- message ID
- unique tracking URL/token
- raw `.eml`
- original attachment

## Blocking note

Shared infrastructure should not be blocked broadly just because it appeared in the redirect chain. Defensive controls should focus on the confirmed suspicious destination and campaign-specific indicators.
