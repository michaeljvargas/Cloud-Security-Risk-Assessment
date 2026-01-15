# Cloud Misconfiguration Findings

Each finding documents a common cloud security misconfiguration, its associated risk, and recommended preventive and detective controls. Findings are based on widely observed cloud security failures in financial services environments.

---

## F-01: Publicly Accessible Object Storage

**What is misconfigured**  
Object storage is configured with public read or write access or lacks restrictive access policies.

**Why it matters**  
Public storage exposure can lead to unauthorized access to customer PII and financial data, triggering regulatory notification requirements, legal exposure, and reputational damage.

**Example attack scenario**  
An external actor enumerates publicly accessible storage endpoints and downloads customer data files exposed due to misconfigured permissions.

**Recommended fix**  
Block all public access, enforce least-privilege bucket policies, and require encryption at rest.

**Preventive control**  
Storage guardrails, encryption-by-default policies, policy-as-code enforcement.

**Detective control**  
Storage access logging, cloud posture monitoring alerts, anomaly detection for unauthorized access.

---

## F-02: Over-Permissive IAM Roles

**What is misconfigured**  
Cloud IAM roles include wildcard permissions or broad administrative privileges beyond job requirements.

**Why it matters**  
Over-permissive IAM significantly increases blast radius if credentials are compromised, enabling privilege escalation and unrestricted data access.

**Example attack scenario**  
A phishing attack compromises employee credentials that grant excessive permissions, allowing the attacker to create access keys and exfiltrate data.

**Recommended fix**  
Conduct least-privilege reviews, separate administrative roles, and restrict sensitive permissions.

**Preventive control**  
IAM policy reviews, role separation, privileged access management workflows.

**Detective control**  
Audit logging for permission changes, alerts on privilege escalation or key creation.

---

## F-03: Internet-Exposed Administrative Access

**What is misconfigured**  
Administrative ports and management interfaces are exposed directly to the internet.

**Why it matters**  
Internet-exposed admin access increases susceptibility to brute force attacks, credential stuffing, and exploitation of unpatched services.

**Example attack scenario**  
An attacker discovers exposed management ports and attempts credential brute forcing or exploits known vulnerabilities.

**Recommended fix**  
Restrict administrative access to private networks, VPNs, or bastion hosts with MFA.

**Preventive control**  
Default-deny inbound policies, network segmentation, private endpoints.

**Detective control**  
Network flow logs, intrusion detection alerts, failed authentication monitoring.

---

## F-04: Missing Centralized Logging and Monitoring

**What is misconfigured**  
Authentication, API, and administrative activity logs are not centralized or consistently retained.

**Why it matters**  
Lack of centralized logging delays threat detection, increases time to containment, and limits incident investigation capabilities.

**Example attack scenario**  
An attacker maintains persistence without detection because suspicious authentication and API activity is not logged or monitored centrally.

**Recommended fix**  
Enable audit logging across all services and centralize logs into a SIEM with defined alerting use cases.

**Preventive control**  
Logging standards, baseline configuration enforcement.

**Detective control**  
SIEM detections, alert tuning, log ingestion and retention monitoring.

---

## F-05: Weak Encryption and Key Management

**What is misconfigured**  
Data is not encrypted at rest, encryption keys are not rotated, or key usage is overly permissive.

**Why it matters**  
Weak encryption increases breach impact and may violate regulatory and compliance expectations.

**Example attack scenario**  
An attacker accesses unencrypted storage or misuses poorly protected encryption keys to decrypt sensitive data.

**Recommended fix**  
Enforce encryption using managed key services, rotate keys regularly, and restrict key access.

**Preventive control**  
Encryption-by-default policies, key management guardrails.

**Detective control**  
Alerts for unencrypted resources, key usage monitoring, and key policy change alerts.

---

## F-06: Secrets Stored in Plain Text

**What is misconfigured**  
API keys, credentials, or tokens are stored in configuration files, code repositories, or plain text storage.

**Why it matters**  
Plain-text secrets enable rapid compromise if systems or repositories are accessed by unauthorized actors.

**Example attack scenario**  
An attacker gains access to a repository or server and retrieves exposed credentials, enabling lateral movement and data access.

**Recommended fix**  
Store secrets in a dedicated secrets management service and rotate credentials regularly.

**Preventive control**  
Secrets management enforcement, automated rotation, repository scanning.

**Detective control**  
Alerts on abnormal secret access and usage patterns.

---

## F-07: Insufficient Backup and Recovery Controls

**What is misconfigured**  
Backups exist but are not tested, retention policies are weak, or backup deletion is not restricted.

**Why it matters**  
Insufficient backup controls increase downtime risk and amplify the impact of ransomware or data corruption incidents.

**Example attack scenario**  
An attacker deletes or encrypts backups, preventing recovery and extending operational outage.

**Recommended fix**  
Implement immutable backups, restrict deletion permissions, and conduct regular restore testing.

**Preventive control**  
Backup guardrails, access restrictions, immutable storage.

**Detective control**  
Alerts on backup deletion, retention changes, and restore failures.
