
# Phishing Email Investigation

## Objective
Document a repeatable process for triaging a suspicious email.

## Investigation steps
1. Record the reported subject, sender, recipient,
   and received timestamp using sanitized sample data.
2. Review email headers and the sending infrastructure.
3. Evaluate SPF, DKIM, and DMARC results.
4. Inspect URLs and attachment metadata safely.
5. Correlate with mail security alerts and SIEM telemetry.
6. Assess scope, severity, and possible user interaction.
7. Recommend appropriate containment and remediation.

## Example findings template
- Alert source:
- Sender and recipient:
- Authentication results:
- URL or attachment indicators:
- Related security alerts:
- User interaction confirmed:
- Impact assessment:
- Recommended actions:
- Escalation decision:

## Response options
Depending on evidence and authorization:
- Quarantine or remove confirmed malicious messages.
- Block confirmed malicious indicators through approved controls.
- Reset credentials or revoke sessions if account compromise
  is suspected and the response procedure calls for it.
- Notify affected users and document actions.

## Safety
Use sanitized samples and approved analysis environments.
Do not open suspicious attachments on a normal workstation
or publish personal information from real email headers.

## Learning outcome
Practiced email triage, authentication checks,
evidence documentation, and response planning.
