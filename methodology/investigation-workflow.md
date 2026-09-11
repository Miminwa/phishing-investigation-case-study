# Investigation Workflow

This page documents the repeatable process used in the case.

## 1. Preserve the original message

Request the original `.eml` or equivalent raw message rather than a forwarded copy. The original preserves routing headers, authentication results, message IDs, MIME boundaries, and attachment metadata.

## 2. Review the headers

Check:

- `From`
- `Return-Path`
- `Received`
- SPF
- DKIM
- DMARC
- sending platform
- message ID

Do not treat a pass result as proof that the message is safe.

## 3. Inspect the MIME structure

Confirm:

- message body type
- attachment names
- attachment MIME types
- transfer encoding
- whether additional objects are embedded

## 4. Analyze the attachment statically

For PDFs, inspect:

- metadata
- hyperlinks
- JavaScript
- embedded files
- forms/actions
- visible-link versus actual-link mismatch

Avoid opening suspicious links from a normal workstation.

## 5. Extract and defang URLs

Record the exact link privately for investigation, but use defanged notation in public documentation, for example:

`example[.]com`

## 6. Analyze redirects remotely

Use a remote analysis service or an isolated environment to observe:

- HTTP redirects
- effective destination
- domain age
- DNS/IP information
- TLS information
- page response
- linked resources

## 7. Assess user exposure

Confirm whether the recipient:

- clicked the link
- entered credentials
- downloaded anything
- reused a password
- has MFA/2FA enabled

## 8. Containment and scoping

Search mail logs for matching indicators such as:

- sender
- subject pattern
- attachment name
- final destination domain
- campaign wording

Quarantine matching messages where appropriate.

## 9. Preserve evidence

Keep internal copies of:

- original `.eml`
- suspicious attachment
- screenshots
- extracted URLs
- hashes
- remote-analysis results
- timeline and analyst notes

Do not publish sensitive originals in a public repository.

## 10. Document limitations

State clearly what was not proven. In this case, the final web server was unavailable during analysis, so the final landing-page behavior could not be observed directly.
