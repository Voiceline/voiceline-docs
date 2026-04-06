# Feature Freeze SOT — Project Overview

## What this project is

This project transforms the VoiceLine documentation repository into the **single source of truth for what sales can sell and what solutions architects can configure and implement**.

It is the operational backbone of the feature freeze initiative. Once complete:
- Contracts reference these docs directly
- Sales can point to module pages to show exactly what is included
- SAs can point to implementation pages to show exactly what can be configured
- Customers who demand scope beyond what's documented are told: read the docs
- Any customisation that isn't covered here is explicitly not in scope unless it passes the product investment criteria

## Problem this solves

- Sales overselling features and capabilities that don't exist or require custom builds
- SAs replicating flawed customer CRM processes instead of implementing VoiceLine's standard
- Customers expecting "magic AI" with infinite customisability
- Roadmaps being cannibalised by free, non-value-adding custom solutions built for individual customers
- Inconsistent answers from SAs on data sync, security, and implementation questions

## Success criteria

1. Every module and its included features is documented with pricing
2. Every FSF workflow has a documented standard implementation (CRM-agnostic)
3. The component library is documented inline — SAs and customers know exactly what's configurable
4. The 90-day FSF-only rollout rule is stated explicitly and linkable
5. Data sync behaviour is documented per CRM (setup, objects synced, field mappings)
6. Security & compliance questions are answered with a single page + trust centre link
7. SAs are actively maintaining and contributing to the implementation section
8. The docs are access-controlled and distributed to customers post-sales-conversation

## Constraints

- All docs are access-controlled (Mintlify password protection or equivalent)
- No public access before a sales conversation
- Pricing is included — this is intentional
- Standard implementations are CRM-agnostic for now; CRM-specific variants follow in a later phase
- Engineering input required for data sync field mappings and retention periods

## Who owns what

| Section | Owner | Notes |
|---------|-------|-------|
| Getting Started | Product (Lino) | Existing — minimal changes |
| Product | Product (Lino) | Existing — minor callout additions |
| Modules & Pricing | Product (Lino) + Sales | Pricing feedback loop with sales |
| Implementation — Our Approach | Product (Lino) | Sets the methodology frame |
| Implementation — Standard Implementations | SAs + Product | SAs document CRM specifics; product owns standards |
| Implementation — Product Customisation | Product (Lino) | Product owns the criteria |
| Implementation — Data & Integrations | Engineering + SAs | Engineering confirms accuracy |
| Implementation — Security & Compliance | SAs | SA-maintained; engineering confirms |
| Integrations | Engineering + SAs | Engineering for data sync; SAs for standard impls |

## Related resources

See [external_knowledge_index.md](./external_knowledge_index.md) for all source material locations.

## Project initiated

2026-04-04 by Lino (CPO)
