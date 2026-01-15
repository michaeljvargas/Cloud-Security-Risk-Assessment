# Cloud Misconfiguration Findings

Each finding documents a common cloud security misconfiguration, its associated risk, and recommended controls. Findings are based on industry-standard cloud security risks observed in financial services environments.

## F-01: Publicly Accessible Object Storage

**What is misconfigured**  
Object storage is configured with public read or write access or lacks restrictive bucket policies.

**Why it matters**  
Public storage exposure can result in unauthorized access to customer PII and financial data, triggering regulatory reporting obligations and reputational damage.

**Example attack scenario**  
An external actor enumerates public storage endpoints and downloads customer data files exposed due to misconfigured access permissions.

**Recommended fix**  
Block all public access to object storage, enforce least-privilege bucket policies, and require encryption at rest.

**Preventive control**  
Cloud storage guardrails, encryption-by-default policies, and policy-as-code enforcement.

**Detective control**  
Storage access logging, cloud posture monitoring alerts, and anomaly detection for unauthorized access.
