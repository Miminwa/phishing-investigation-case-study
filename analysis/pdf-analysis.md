# PDF Analysis

## Attachment role

The PDF acted as the social-engineering lure. It presented itself as a secure payment/remittance document and directed the recipient toward an external resource.

## Static findings

The most important finding was a mismatch between the address presented to the recipient and the actual hyperlink embedded in the PDF.

The document visually suggested an Adobe-style document destination, while the embedded link pointed elsewhere.

That mismatch is a strong phishing indicator because it creates a false sense of trust around the destination.

## Embedded content

Initial static review did not identify embedded JavaScript, executable content, or an additional embedded payload inside the PDF.

Based on the evidence available, the PDF appears to have been primarily a link-delivery mechanism rather than a self-contained malware payload.

## Analyst handling

The embedded URL was extracted and analyzed without opening the destination from a normal user workstation.

## Conclusion

The attachment itself provided enough evidence to justify escalation to URL analysis. The deceptive link behavior was more significant than the file format itself.
