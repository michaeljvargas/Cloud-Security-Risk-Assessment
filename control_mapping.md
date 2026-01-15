# Control Mapping

## Approach
Each cloud misconfiguration finding is mapped to preventive and detective controls aligned with the NIST Cybersecurity Framework and CIS Critical Security Controls.

## Control Mapping Table

| Finding ID | Preventive Controls | Detective Controls | NIST CSF | CIS Controls |
|-----------|---------------------|--------------------|----------|--------------|
| F-01 | Block public access, encryption by default | Access logs, posture alerts | PR.DS, DE.CM | CIS 3 |
| F-02 | Least privilege IAM, PAM | Privilege change alerts | PR.AC, DE.CM | CIS 5, 6 |
| F-03 | Default deny inbound, private admin access | Flow logs, failed login alerts | PR.AC | CIS 4 |
| F-04 | Logging standards, baseline configs | SIEM detections, alert tuning | DE.CM, RS.AN | CIS 8 |
| F-05 | KMS encryption, key rotation | Key usage and policy alerts | PR.DS | CIS 3 |
| F-06 | Secrets manager, rotation | Secrets access anomaly alerts | PR.AC | CIS 5 |
| F-07 | Immutable backups, access restrictions | Backup deletion and failure alerts | PR.IP, RC.RP | CIS 11 |

