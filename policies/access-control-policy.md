# Access Control Policy — 16: No-Code Access Orchestration with Okta Workflows & Event Hooks

**Classification:** Internal Use - Portfolio Demonstration
**Policy Owner:** Identity & Access Management (IAM) Engineering
**Effective Date:** 2026-08-24
**Review Cycle:** Annual
**Version:** 1.0

## 1. Purpose

This policy establishes the mandatory controls governing the architecture described in "No-Code Access Orchestration with Okta Workflows & Event Hooks", in support of the compliance obligations listed in Section 6 and the risk position documented in the associated Compliance Mapping.

## 2. Scope

This policy applies to all personnel, systems, and third parties with access to the in-scope environment: Okta, Okta Workflows, Okta Event Hooks, Okta Group Rules. It applies regardless of employment classification (employee, contractor, or third party) where such access is technically possible.

## 3. Policy Statements

1. Department-based (or equivalent attribute-based) group membership shall be governed by Group Rules rather than manual assignment, wherever the underlying attribute is reliably maintained.
2. Access-related automation (notification, conditional routing) shall be implemented using Okta's native Workflows engine in preference to custom-built backend services, unless a documented technical requirement cannot be met natively.
3. Any workflow with conditional branching shall have both branches explicitly tested and evidenced, not only the expected/happy path.
4. External systems requiring real-time notification of identity lifecycle events shall be integrated via Event Hooks rather than scheduled polling.
5. Event Hook endpoints shall be verified at setup and shall be reviewed for continued validity if the receiving system changes ownership or infrastructure.

## 4. Roles & Responsibilities

| Role | Responsibility |
|---|---|
| Identity & Access Management (IAM) Engineering | Owns this policy, approves exceptions, and is accountable for control testing outcomes. |
| System/Application Owner | Ensures the in-scope system is configured in accordance with this policy at all times. |
| Requesting Individual | Complies with the access request and justification process defined in this policy. |
| Internal Audit / Compliance | Independently verifies control operating effectiveness per the testing procedure in `compliance/compliance-mapping.md`. |

## 5. Exceptions

Any deviation from the policy statements in Section 3 requires a documented, time-bound exception, approved in writing by Identity & Access Management (IAM) Engineering, with a defined expiry date and a compensating control where applicable. Exceptions shall be logged and reviewed at each policy review cycle.

## 6. Related Standards & Requirements

- ISO 27001 A.9.2.2 - User access provisioning
- ISO 27001 A.12.4 - Logging and monitoring

## 7. Enforcement

Non-compliance with this policy is treated as a control deficiency and shall be logged, tracked, and remediated per the Non-Conformance Handling process defined in `compliance/compliance-mapping.md`. Repeated or willful non-compliance may result in access revocation pending review.

## 8. Document Control

| Version | Date | Author | Change Summary |
|---|---|---|---|
| 1.0 | 2026-08-24 | Identity & Access Management (IAM) Engineering | Initial approved version. |

---

[⬅ Back to project README](../README.md)
