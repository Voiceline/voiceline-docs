# Sources Scanned

Running log of every source file or page read during research. Check this **before** reading any source — it may already be covered.

**How to use**: Before reading a backend file, Figma file, or Notion page, search here first. If it's already logged, use the key findings instead of re-reading.

---

## Index

| Source | Type | Read during | Features covered | Key findings |
|--------|------|-------------|-----------------|--------------|
| `product_documentation/01_features/playbooks/` (tree) | KB | Batch 2 | playbooks overview, builder, analytics | Distributed by industry/territory/rep. Beta. FSF bundle (fundamentals tier) + Coaching Pro (pro tier). Sub-features: single_playbook, multi_playbook_distribution, analytics. |
| `product_documentation/01_features/visit_performance_dashboard/` | KB | Batch 2 | visit analytics — visit performance | Positive vs. negative visits (offers, orders, opps). Manager view. Live. FSF bundle. |
| `product_documentation/01_features/personal_coaching_reports/` | KB | Batch 2 | personal profiles (team activity) | Per-rep patterns vs. top performers. Backlog. |
| `voiceline_api/analytics/next_insight/richness_analytics.go` | Backend | Batch 2 | visit richness, playbook analytics | Richness 0–1: 3 base criteria (outcome, products, customer situation) + bonus via percentile. 5 categories total. |
| `voiceline_api/analytics/next_insight/personal_richness_radar.go` | Backend | Batch 2 | visit richness per-rep, personal profiles | 5-category radar: Meeting outcome, Competition, Customer development, Products, Service. Rep vs. workspace avg. |
| `voiceline_api/analytics/next_insight/rule_library.go` | Backend | Batch 2 | playbook rules, richness scoring | Rules in rules.toml + hierarchy.toml. TOML-based — no UI builder API found (may be elsewhere). |
| `voiceline_frontend/src/routes/_auth/analytics/playbook.tsx` | Frontend | Batch 2 | playbook analytics | Route `/analytics/playbook/performance`. Tabs: Performance + Answers. Flag: AnalyticsFeature.Playbook (7). Manager-only. |
| `voiceline_frontend/src/routes/_auth/analytics/activity/visits/richness.tsx` | Frontend | Batch 2 | visit richness | Route `/analytics/activity/visits/richness`. Label "Visit Richness". Beta. Flags: RichnessAnalytics (3) + PersonalRichnessRadar (4). |
| `voiceline_frontend/src/Menu/Menuv2.tsx` | Frontend | Batch 2 | visit insight feed, team activity nav | "Visit insight feed" (DE: Besuchs-Insights Feed) at `/analytics/activity/visits`. Beta. Flag: VisitInsights (2). |
| `voiceline_flutter/lib/widget/playbook/playbook_overview.dart` | Mobile | Batch 2 | playbooks (rep/mobile) | In recorder UI top section during visit. Label "Playbook". Shows deduplicated questions + long-press for details. Flag: `hasPlaybooks`. |

| `product_documentation/01_features/post_meeting_voice_debriefing/` | KB | Batch 6 | assistant — app functionality | Core capture: rep calls assistant post-meeting, speaks naturally, AI creates CRM docs. 5 min vs 15-20 min manual. |
| `product_documentation/01_features/voice_memo_mode/` | KB | Batch 6 | assistant — app functionality | Quick voice note while driving. 3-5 captures/day. Not a full visit report. |
| `product_documentation/01_features/industry_fair_mode/` | KB | Batch 6 | assistant — fair mode | Live. "Messe" in code. Reps scan business cards + record voice at fairs. 50-100 leads/rep/day. |
| `product_documentation/01_features/business_card_scanner/` | KB | Batch 6 | assistant — images/business cards | Live. OCR/AI extracts contact fields. Dedup detection. Syncs to CRM + optionally mobile contacts. |
| `product_documentation/01_features/fair_report/` | KB | Batch 6 | assistant — fair mode | Backlog. Fair-specific structured report template. ActionType 12 exists in code. |
| `product_documentation/01_features/industry_fair_analytics/` | KB | Batch 6 | analytics — competitor analytics (cross-ref) | Backlog. Fair ROI dashboard. 14-17 fairs/year. |
| `voiceline_flutter/` (fair mode screens) | Mobile | Batch 6 | assistant — fair mode, onboarding, images | Fair mode: AppMode.messe toggle, "Scan & Record" CTA, fair header banner. Onboarding: password→phone→voice→consent. Business card: /scan route, front+back capture, "Add recording" or "Save and finish". |
| `voiceline_frontend/src/routes/_auth/messe/` | Frontend | Batch 6 | assistant — fair mode (manager) | Web: /messe/list (Upcoming/Ongoing/Completed), /messe/new, /messe/edit. Fair fields: name, dates, tracking ID, participants. |
| `voiceline_api/` (fair + credits) | Backend | Batch 6 | assistant — fair mode, call credits | Messe model: ID, name, startTime, endTime, workspaceID, participants. Credit: VoicelineCreditBalance (monthly minutes). ActionType 12 = FairReport. |

---

*Last updated: 2026-03-03*
| visit_report_creation.md | KB feature | product_documentation/01_features/visit_report_creation/ | Batch 1 | 2026-03-06 |
| call_log.md | KB feature | product_documentation/01_features/call_log/ | Batch 1 | 2026-03-06 |
| task_creation.md | KB feature | product_documentation/01_features/task_creation/ | Batch 1 | 2026-03-06 |
| email_writing.md | KB feature | product_documentation/01_features/email_writing/ | Batch 1 | 2026-03-06 |
| reminder_creation.md | KB feature | product_documentation/01_features/reminder_creation/ | Batch 1 | 2026-03-06 |
| meeting_creation.md | KB feature | product_documentation/01_features/meeting_creation/ | Batch 1 | 2026-03-06 |
| opportunity_creation.md | KB feature | product_documentation/01_features/opportunity_creation/ | Batch 1 | 2026-03-06 |
| opportunity_update.md | KB feature | product_documentation/01_features/opportunity_update/ | Batch 1 | 2026-03-06 |
| lead_creation.md | KB feature | product_documentation/01_features/lead_creation/ | Batch 1 | 2026-03-06 |
| account_creation.md | KB feature | product_documentation/01_features/account_creation/ | Batch 1 | 2026-03-06 |
| account_update.md | KB feature | product_documentation/01_features/account_update/ | Batch 1 | 2026-03-06 |
| contact_creation.md | KB feature | product_documentation/01_features/contact_creation/ | Batch 1 | 2026-03-06 |
| fill_survey.md | KB feature | product_documentation/01_features/fill_survey/ | Batch 1 | 2026-03-06 |
| survey_mode.md | KB feature | product_documentation/01_features/survey_mode/ | Batch 1 | 2026-03-06 |
| case_creation.md | KB feature | product_documentation/01_features/case_creation/ | Batch 1 | 2026-03-06 |
| case_status.md | KB feature | product_documentation/01_features/case_status/ | Batch 1 | 2026-03-06 |
| standard-workflows.go | Backend | voiceline_api/scripts/standard-templates/ | Batch 1 | 2026-03-06 |
| library.toml | Backend | voiceline_api/handlers/action_management/reportbuilder/library/ | Batch 1 | 2026-03-06 |
| vl_actions.go | Backend | voiceline_api/types/action_types/ | Batch 1 | 2026-03-06 |
| visit_performance_dashboard.md | KB feature | product_documentation/01_features/visit_performance_dashboard/ | Batch 3 | 2026-03-06 |
| personal_coaching_reports.md | KB feature | product_documentation/01_features/personal_coaching_reports/ | Batch 3 | 2026-03-06 |
| conversational_coaching.md | KB feature | product_documentation/01_features/conversational_coaching/ | Batch 3 | 2026-03-06 |
| analytics/activity/index.tsx | Frontend | voiceline_frontend/src/routes/_auth/analytics/activity/ | Batch 3 | 2026-03-06 |
| analytics/activity/team/$userId.tsx | Frontend | voiceline_frontend/src/routes/_auth/analytics/activity/team/ | Batch 3 | 2026-03-06 |
| analytics/activity/visits/index.tsx | Frontend | voiceline_frontend/src/routes/_auth/analytics/activity/visits/ | Batch 3 | 2026-03-06 |
| AnalyticsTabNav.tsx | Frontend | voiceline_frontend/src/components/analytics/_components/team-activity/ | Batch 3 | 2026-03-06 |
| customer_activity_summary.md | KB feature | product_documentation/01_features/customer_activity_summary/ | Batch 5 | 2026-03-06 |
| crm_quality_checks.md | KB feature | product_documentation/01_features/crm_quality_checks/ | Batch 5 | 2026-03-06 |
| cross_selling_recommendations.md | KB feature | product_documentation/01_features/cross_selling_recommendations/ | Batch 5 | 2026-03-06 |
| update_account_potential.md | KB feature | product_documentation/01_features/update_account_potential/ | Batch 5 | 2026-03-06 |
| visit_prep_settings.dart | Mobile | voiceline_flutter/lib/route/profile/visit_prep/ | Batch 5 | 2026-03-06 |
| event_notification.dart | Mobile | voiceline_flutter/lib/model/ | Batch 5 | 2026-03-06 |
| deduplication_information.go | Backend | voiceline_api/handlers/action_management/reportbuilder/library/ | Batch 5 | 2026-03-06 |
| competitor_dashboard.md | KB feature | product_documentation/01_features/competitor_dashboard/ | Batch 4 | 2026-03-06 |
| analytics/market-intelligence/competitors/index.tsx | Frontend | voiceline_frontend/src/routes/_auth/analytics/market-intelligence/competitors/ | Batch 4 | 2026-03-06 |
| MarketIntelligenceTabNav.tsx | Frontend | voiceline_frontend/src/components/analytics/_components/market-intelligence/ | Batch 4 | 2026-03-06 |
| crm/types/crmcortext.go | Backend | voiceline_api/crm/types/ | Batch 7 | 2026-03-06 |
| crm/sap/v1/ (file listing) | Backend | voiceline_api/crm/sap/v1/ | Batch 7 | 2026-03-06 |
| crm/sap/v2/ (file listing) | Backend | voiceline_api/crm/sap/v2/ | Batch 7 | 2026-03-06 |
| crm/salesforce/ (file listing) | Backend | voiceline_api/crm/salesforce/ | Batch 7 | 2026-03-06 |
| crm/dynamics/ (file listing) | Backend | voiceline_api/crm/dynamics/ | Batch 7 | 2026-03-06 |
| crm/aurea/ (file listing) | Backend | voiceline_api/crm/aurea/ | Batch 7 | 2026-03-06 |
| crm/zoho/ (file listing) | Backend | voiceline_api/crm/zoho/ | Batch 7 | 2026-03-06 |
| crm/hubspot/ (file listing) | Backend | voiceline_api/crm/hubspot/ | Batch 7 | 2026-03-06 |
| crm/auth/passwordauth.go | Backend | voiceline_api/crm/auth/ | Batch 7 | 2026-03-06 |
| crm/auth/oauth2.go | Backend | voiceline_api/crm/auth/ | Batch 7 | 2026-03-06 |
| workspace-settings/integrations.tsx | Frontend | voiceline_frontend/src/routes/_auth/workspace-settings/ | Batch 7 | 2026-03-06 |
| search/client/schemas.go (WorkspaceSchemaV14) | Backend | voiceline_api/search/client/ | Batch 8 | 2026-03-06 |
| crm/types/crmcortext.go (Destination enum) | Backend | voiceline_api/crm/types/ | Batch 8 | 2026-03-06 |
| workspace-settings/competitors.tsx | Frontend | voiceline_frontend/src/routes/_auth/workspace-settings/ | Batch 8 | 2026-03-06 |
| assembly/workspace-info.go (WorkspaceInfo struct) | Backend | voiceline_api/assembly/ | Batch 9 | 2026-03-06 |
| WorkspaceSettings/Administration/Administration.tsx | Frontend | voiceline_frontend/src/WorkspaceSettings/ | Batch 9 | 2026-03-06 |
| WorkspaceSettings/User Management/UserManagement.tsx | Frontend | voiceline_frontend/src/WorkspaceSettings/ | Batch 9 | 2026-03-06 |
| WorkspaceSettings/Integrationsv2/authType.tsx | Frontend | voiceline_frontend/src/WorkspaceSettings/ | Batch 9 | 2026-03-06 |
| search/client/search-builder.go | Backend | voiceline_api/search/client/ | Batch 9 | 2026-03-06 |
| routes/vocab-routes.go | Backend | voiceline_api/routes/ | Batch 9 | 2026-03-06 |
