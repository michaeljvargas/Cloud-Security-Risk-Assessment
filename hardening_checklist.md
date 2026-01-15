# Cloud Hardening Checklist

## Identity and Access
Enforce least privilege on all IAM roles
Require MFA for privileged accounts
Disable long-lived access keys
Review administrative access quarterly

## Network Security
Default deny inbound traffic
Restrict admin access to VPN or bastion hosts
Use private endpoints for data services
Enable network flow logs

## Data Protection
Encrypt data at rest and in transit
Block public access to object storage
Restrict data exports
Apply data classification controls

## Logging and Monitoring
Enable audit logs for IAM, API, and admin actions
Centralize logs in SIEM
Create detections for credential abuse and privilege changes
Monitor log ingestion and retention

## Secrets Management
Store secrets in a secrets manager
Rotate secrets regularly
Enable repository and secrets scanning

## Resilience and Recovery
Implement immutable backups
Restrict backup deletion permissions
Test restore procedures regularly
Alert on backup failures and changes

