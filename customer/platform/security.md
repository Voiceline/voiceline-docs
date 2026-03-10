---
status: Live
last_updated: 2026-03-06
---

# Security & Compliance

Authentication options and data protection configuration for VoiceLine.

## Overview

VoiceLine supports multiple authentication methods to fit your organization's security requirements — from simple email/password to full SSO integration with your identity provider. Data protection settings let you configure consent flows for recording in regulated environments.

## Where to find it

Go to **Workspace Settings** → **Integrations** to configure CRM authentication. VoiceLine user authentication is configured by your account manager during workspace setup.

## Authentication methods

VoiceLine supports the following authentication methods for both the mobile app and web application:

| Method | Description |
|--------|-------------|
| **Password** | Email + password. User credentials managed in VoiceLine. |
| **Password with domain** | Email + password, scoped to a specific domain or subdomain. |
| **OAuth 2.0** | Standard OAuth flow via your identity provider. |
| **OAuth with domain** | OAuth scoped to your organization's domain. |
| **SSO (OAuth with domain)** | Single Sign-On using your corporate identity provider (Azure AD, Okta, etc.). |

The authentication method is configured per workspace by your VoiceLine account manager. Contact your account manager to change authentication settings.

### CRM authentication

CRM integrations use separate credentials from VoiceLine user authentication. See [Integrations](./integrations/index.md) for CRM-specific auth configuration.

## Data processing consent

For workspaces operating in regulated environments (GDPR, etc.), VoiceLine can display a data processing consent prompt to reps before they begin recording.

**Consent settings** are managed via `DataProtectionSettings` in your workspace configuration — contact your VoiceLine account manager to enable or configure this feature.

When enabled, reps must acknowledge the consent notice before each recording session. Consent timestamps are logged.

## Data storage

- Voice recordings and transcripts are stored in AWS (encrypted at rest and in transit)
- CRM credentials are encrypted at rest in VoiceLine's database
- Data residency options: contact your account manager for EU data residency requirements

## FAQ

**Does VoiceLine support SAML SSO?**
VoiceLine supports OAuth 2.0-based SSO. SAML-specific integrations are evaluated per customer — contact your account manager.

**Can reps use VoiceLine without a corporate identity provider?**
Yes — password authentication is always available as a fallback when SSO is not configured.

**Is VoiceLine GDPR compliant?**
VoiceLine processes data in accordance with GDPR. A Data Processing Agreement (DPA) is available — contact your account manager.

**Who manages VoiceLine user passwords?**
For password auth: users set their own password via the invitation email. Admins can trigger a password reset from **User Management**.
