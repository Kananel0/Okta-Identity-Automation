# Compliance Mapping — 16: No-Code Access Orchestration with Okta Workflows & Event Hooks

**Classification:** Internal Use - Portfolio Demonstration
**Control Owner:** Identity & Access Management (IAM) Engineering
**Testing Frequency:** Annual (or per the cadence stated in the governing policy, where more frequent)

## Control Objectives

| Requirement | Description |
|---|---|
| ISO 27001 A.9.2.2 | User access provisioning |
| ISO 27001 A.12.4 | Logging and monitoring |

## Implementation Narrative

- Configured attribute-driven Group Rules so department-based access assignment happens automatically on profile changes, with no manual group management.
- Built a no-code Okta Workflows automation triggered on group membership change, sending a contextual notification with zero custom backend code or hosted service required.
- Built a second, branching Workflow triggered on user creation, routing new hires to the correct access path and notification based on department - demonstrating conditional orchestration logic, not just a single trigger-to-action chain.
- Configured a real-time Event Hook delivering a live webhook payload to an external system the instant a user is deactivated, proving event-driven integration without polling or custom API development.

## Control Testing Procedure

The following steps constitute the minimum testing procedure to be performed by the control owner, or by internal/external audit, to assess operating effectiveness:

1. Trigger the group-assignment flow by changing a test user's department attribute and confirm both the automatic group membership change and the resulting notification are logged in Workflow execution history.
2. Create a test user matching the conditional branch criteria and a second test user that does not match, and confirm each produces the correct, distinct branch outcome in execution history.
3. Deactivate a test user and confirm the Event Hook delivers a payload to the subscribed external endpoint within seconds, with the payload content matching the actual event.

## Evidence Artifacts

The following evidence shall be retained and made available on request to support control testing:

- Group Rule expression and resulting automatic group membership
- Workflow canvas views for both flows, including the full branching logic of the conditional flow
- Workflow execution history showing successful runs for each trigger and each branch outcome
- Event Hook configuration (active status, subscribed event) and the corresponding delivered payload at the receiving endpoint

## Risk Assessment

**Inherent risk:** Access-governance automation requiring custom code creates both a delivery bottleneck (dependent on engineering capacity) and an ongoing maintenance liability, increasing the likelihood that useful automation simply doesn't get built, leaving processes manual and error-prone by default.

**Residual risk (control in place):** Low. Group assignment, conditional routing, and real-time external notification are all implemented natively, with Okta-managed execution history providing the audit trail. Residual risk relates to Event Hook endpoint availability on the receiving system's side, which is outside Okta's control and should be monitored independently by the receiving system's owner.

## Non-Conformance Handling

Any control testing result that fails one or more steps above shall be logged as a non-conformance, assigned to Identity & Access Management (IAM) Engineering, and remediated on a timeline commensurate with the residual risk rating. Non-conformances open longer than thirty (30) days shall be escalated per the organization's risk acceptance process.

---

[⬅ Back to project README](../README.md)
