# AWS Security Control Plan

## 1. Purpose

This document defines proposed cloud security controls for the simulated MediSecure UAE healthcare environment.

## 2. Identity and Access Management

### Objectives

Restrict access to approved users and services according to their responsibilities.

### Proposed Controls

- Apply least-privilege permissions to users, groups, and service roles.
- Require MFA for privileged accounts and other accounts according to risk and policy.
- Use role-based temporary credentials where appropriate instead of long-lived access keys.
- Review permissions periodically and remove unnecessary access.
- Separate administrative access from routine user access.
- Document account provisioning and removal procedures.

### Evidence to Collect

- IAM policies and role definitions.
- MFA configuration.
- Access review records.
- Results of permission tests.

## 3. Network Security

### Objectives

Reduce unnecessary network exposure and restrict communication between application components.

### Proposed Controls

- Separate public-facing entry points from private application and data resources.
- Restrict inbound traffic to required ports and trusted sources.
- Restrict outbound traffic according to application requirements.
- Avoid exposing databases directly to the public internet.
- Review network access rules periodically.
- Document permitted communication paths.

### Evidence to Collect

- Architecture and data-flow diagram.
- VPC subnet configuration.
- Security-group rules.
- Authorized connectivity test results.

## 4. Data Protection

### Objectives

Protect sensitive health information against unauthorized access, disclosure, and loss.

### Proposed Controls

- Classify patient information as sensitive.
- Block public access to storage containing sensitive records.
- Enable and verify encryption at rest.
- Require secure transport for data transfers.
- Restrict access to approved identities and applications.
- Define data retention, secure disposal, and backup procedures.
- Protect access to encryption keys.

### Evidence to Collect

- Storage configuration.
- Access policies.
- Encryption settings.
- Secure transport configuration.
- Backup and recovery test results.

## 5. Security Monitoring

### Objectives

Record relevant activity and support timely investigation of suspicious events.

### Proposed Controls

- Enable appropriate AWS audit logging.
- Enable relevant S3 data-event logging where object-level monitoring is required.
- Protect logs against unauthorized modification or deletion.
- Define alert conditions and investigation procedures.
- Review alerts and record investigation outcomes.
- Integrate log sources with an approved SIEM when available.

### Evidence to Collect

- Logging configuration.
- Sample audit events.
- Alert rules.
- Investigation records.
- Log protection settings.

## 6. Incident Response

### Objectives

Ensure that suspected security incidents are investigated, contained, and documented.

### Proposed Controls

- Define incident severity and escalation contacts.
- Preserve relevant logs and evidence.
- Contain affected identities or resources through approved procedures.
- Assess potential exposure of sensitive information.
- Escalate notification and reporting decisions to appropriate stakeholders.
- Conduct incident-response exercises.

### Evidence to Collect

- Incident-response procedure.
- Escalation matrix.
- Tabletop exercise record.
- Remediation tracking records.

## 7. Backup and Recovery

### Objectives

Reduce the impact of data loss and service disruption.

### Proposed Controls

- Define backup requirements and recovery objectives.
- Restrict access to backup resources.
- Protect backup data against unauthorized deletion.
- Test restoration procedures.
- Document recovery responsibilities.

### Evidence to Collect

- Backup policy.
- Backup configuration.
- Restoration test results.
- Recovery procedure.

## 8. Implementation Status

All controls in this document are proposed until they have been implemented and verified with appropriate evidence.

This document does not demonstrate that any AWS resources have been deployed.