
# Splunk SIEM: Failed Login Investigation

## Objective
Investigate repeated login failures and identify
potentially suspicious source IP addresses.

## Tools
- Splunk Enterprise or an authorized Splunk lab
- Search Processing Language (SPL)

## Sample SPL query

index=security sourcetype=auth_logs
| search action=failure
| stats count AS failed_attempts
        dc(user) AS affected_users
        values(user) AS user_list
  by src_ip
| where failed_attempts >= 10
| sort - failed_attempts

## Investigation workflow
1. Confirm the actual index and sourcetype.
2. Review the source IP, affected users, and timestamps.
3. Search for successful logins from the same source.
4. Correlate with endpoint or identity alerts if available.
5. Document findings and escalation recommendations.

## Limitations
The index, sourcetype, and field names are placeholders.
Adapt them to the data available in your lab.
The threshold may require tuning to reduce false positives.

## Learning outcome
Practiced SPL filtering, stats, distinct counts,
and investigation pivoting.
