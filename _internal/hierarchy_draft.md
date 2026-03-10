# Description
This is supposed to be the high-level folder structure of the product documentation.
I want the first two levels to be available in the left sidebar in the final documentation webapp. All information in Level 3 or higher should be used as input for the markdown file content.
The file content of the individual markdown files should use a template structure. e.g. all workflows should have the same page layout. all CRMs should have same page layout.
Content in () does not exist yet, but can already be added to indicate future docs.
This structure is probably not exhaustive. I might have forgotten functionalities and features.
This structure does not necessarily reflect the code logic. It has been designed to give users a simple plausible navigation throughout our product portfolio.
The namings/ titles of the individual sections are not final and are subject to change. Suggest wording updates where needed or unclear.
Not all content will be easily retrievable and you wont find context for all feature names. Ask clarifying questions for expected content per page if needed.

# Content
**Getting Started**
- Platform Overview
- Quick Start

**Productivity Platform**
- Assistant
    - Onboarding
    - App functionality
    - Call functionality
        - Territories
        - Credits
        - Mailbox
    - Additional context
        - Images
            - (Handwritten notes)
        - Business Cards
            - (QR Codes)
    - Fair Mode
        - Managing Fairs
        - Activating Fair Mode
        - Fair Reports
- Workflows
    - Visit Report
        - Types: create
    - Call Log
    - Task
    - Email
    - Reminder
    - Meeting
    - Opportunity
        - Types: create, update
    - Lead
    - Account
    - Contact
    - Survey
    - Case
- Visit Briefing
    - Activity Summary
        - VoiceLine data
        - (CRM Data)
    - (Cross-Selling)
    - (Order Data)
- Customer Data Quality
    - Lead Creation
        - Lead-to-lead
        - Lead-to-contact
        - Lead-to-account
    - Contact Creation
        - Contact-to-contact
    - Account Creation
        - Account-to-account

**Analytics Platform**
- (Data Lake)
    - Insights
        - Extraction Logic / Industry Taxonomies
    - Dynamic Filters
        - Account, Group, Industry, Product, Competitor, ...
- (AI Analyst)
    - Interface
    - Real-time alerts
- Competitor Analytics
- (Product Analytics)
- (Industry Analytics)

**Coaching Platform**
- Playbooks
    - Overview
    - Builder
    - Analytics
- Team Activity
    - Activity Overview
    - Field Documentation / currently named visit richness
    - Personal Profiles
    - (Sales Productivity)
    - (Pipeline Creation)
    - (Backoffice Communication)
- Visit Analytics
    - Live Feed
    - Visit Performance
    - Visit Richness

**Unified Data Platform**
- Workspace Administration
    - Users Management
        - Creating User
        - Groups & Hierarchies
        - Roles & Permissions
    - Functions
    - Assistant Credits 
- Language Settings
    - Overview
        - Workspace Languages
    - Assistant Languages
    - Custom Vocabulary
        - Internal Vocabulary
        - Products
        - Competitors
        - Customer Names
        - Contact Names
    - Translations
- Security & Compliance
    - Authentication
        - Basic Auth
        - OAuth
        - SSO
    - Data Processing Consent   
        - Constum docs
- Workflow Customisation
    - Overview
    - Basic Schema
        - Intent, Tagging, Parts, title, description, multi-language, mandatory, ...
    - Parts Library
    - Workflow Relations / Joint Submission
- Integrations
    - CRMs
        - SAP C4C v1
            - Sync Frequency
            - Authentication
        - SAP C4C v2
        - Salesforce
        - MS Dynamics
        - Aurea
        - ZOHO
        - Hubspot
    - Authentication
    - Connection Overview
        - API logging
        - Error handling
    - VPNs
- Data Objects
    - Products
        - Search Information
            - Visible
            - Searchable
    - Competitors
    - Accounts
    - Contacts
    - Opportunities
    - Leads
    - Meetings
    - Tasks
    - Industries
    - (Orders)
    - (Offers)
    - (Potential)
- Search Settings
    - Search behavior
        - conversational
        - extended search
    - Scoring Logic
        - Searchable Information
        - Favourites
        - Relations
    - Favourites
        - Objects with favourites
    - Filtering
    - Permissions