# Security Monitoring and Detection Plan

## 1. Objective

Define monitoring scenarios that could help MediSecure UAE identify suspicious access, configuration changes, and potential exposure of sensitive healthcare information.

## 2. Proposed Log Sources

- AWS CloudTrail management events.
- S3 object-level data events for designated sensitive storage.
- Relevant identity-provider authentication events.
- Application authentication and authorization logs.
- Network security logs where applicable.

## 3. Detection Scenario DET-01: Repeated Authentication Failures

**Scenario:** A user account experiences repeated failed authentication attempts.

**Required data:** Account identifier, timestamp, source information, and authentication outcome.

**Investigation:** Review the number and timing of failures, check whether a successful login followed, and determine whether the activity is expected.

**Response:** Investigate the account and follow the approved account-protection procedure if compromise is suspected.

## 4. Detection Scenario DET-02: Unexpected Storage Access

**Scenario:** A sensitive storage object is accessed by an identity that does not normally require it.

**Required data:** Relevant S3 data events, identity, resource identifier, timestamp, and request outcome.

**Investigation:** Verify the identity, business purpose, and permissions.

**Response:** Restrict access if unauthorized activity is confirmed and preserve evidence.

## 5. Detection Scenario DET-03: Storage Security Configuration Change

**Scenario:** A bucket policy or public-access configuration is changed unexpectedly.

**Required data:** Relevant CloudTrail management events and the previous and current configuration.

**Investigation:** Identify who made the change, when it occurred, and whether it was approved.

**Response:** Restore the approved configuration when appropriate and investigate the change.

## 6. Detection Scenario DET-04: Privileged Permission Change

**Scenario:** A privileged identity receives additional permissions unexpectedly.

**Required data:** Relevant IAM management events and change records.

**Investigation:** Determine whether the change was authorized and whether the resulting permissions exceed business needs.

**Response:** Revoke unauthorized changes through the approved change process and review related activity.

## 7. Alert Triage Process

1. Validate the alert and its source.
2. Determine whether the activity is expected.
3. Establish the affected identity, resource, and time period.
4. Assess the potential impact on sensitive information.
5. Escalate according to severity and response procedures.
6. Record the investigation and final disposition.

## 8. Monitoring Limitations

These are proposed detection scenarios. No live SIEM integration or automated detection has been implemented in this documentation-only project.

Detection thresholds and alert rules must be tested and tuned against actual event data before operational use.