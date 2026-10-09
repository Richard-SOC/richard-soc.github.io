
# Microsoft Sentinel: Authentication Threat Detection

## Objective
Practice identifying repeated authentication failures
and investigating possible brute-force activity using KQL.

## Tools
- Microsoft Sentinel
- Log Analytics
- Kusto Query Language (KQL)

## Sample detection query

SigninLogs
| where TimeGenerated > ago(24h)
| where ResultType != "0"
| summarize FailedAttempts = count(),
            TargetAccounts = dcount(UserPrincipalName)
  by IPAddress, bin(TimeGenerated, 15m)
| where FailedAttempts >= 10
| order by FailedAttempts desc

## Investigation workflow
1. Identify IP addresses generating repeated failures.
2. Review affected accounts and event timestamps.
3. Check whether successful sign-ins followed failures.
4. Examine location, device, and other available context.
5. Document evidence and escalate when appropriate.

## Limitations
This is an example detection query, not proof of an attack.
Validate the schema, available fields, baseline activity,
and false positives in your own authorized lab.

## Learning outcome
Practiced KQL filtering, aggregation, time windows,
and authentication alert investigation.

## Data source
SigninLogs is a Microsoft Entra sign-in log table.
A connected data source and appropriate permissions
are required to run the query against real logs.
