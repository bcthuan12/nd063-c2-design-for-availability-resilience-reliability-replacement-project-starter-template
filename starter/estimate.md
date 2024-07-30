1. Minimum RTO for a single AZ outage

| Time  | Description                                                |
| ----- | ---------------------------------------------------------- |
| 00:01 | Problem happens (First minute)                             |
| 00:06 | An amount of time passes before an alert triggers (5 mins) |
| 00:07 | Automatically switch to second availability zone (2 mins)  |

**Total time ±10 mins**

2. Minimum RTO for a single region outage

| Time  | Description                                                |
| ----- | ---------------------------------------------------------- |
| 00:01 | Problem happens (First minute)                             |
| 00:06 | An amount of time passes before an alert triggers (5 mins) |
| 00:07 | Alert triggers (1 mins)                                    |
| 00:17 | On-call staff get to workstation (10 mins)                 |
| 00:27 | On-call staff starts diagnosing the issue (10 mins)        |
| 00:37 | Root cause is discovered (10 mins)                         |
| 00:47 | Remediation started (10 mins)                              |
| 00:52 | Issue fixed (5 mins)                                       |

**Total time ±60 mins**

3. Minimum RPO for a single AZ outage

RDS has point in time restore available which uploads transactions every 5 minutes. Thus, if this is case then the most data that would be lost would be 5 minutes.

4. Minimum RPO for a single region outage

Read replicas aim to be kept up to date with the primary DB so the read replica should have almost the same RPO as the primary DB. For some critical cases we can consider at most the RPO should be ±10 mins.
