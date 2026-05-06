# Standards & API Reference

> Project: SMB Lending Platform · Generated: 2026-05-03

## Industry Standards & Specifications

### Regulatory & Compliance Standards

**Dodd-Frank Act Section 1071 / CFPB Regulation B — Small Business Lending Data Collection**
- Official URL: https://www.consumerfinance.gov/1071-rule/
- The CFPB's 2026 final rule (revised from the 2023 original) requires financial institutions originating 1,000+ covered SMB credit transactions in each of two preceding calendar years to collect and report demographic and pricing data. First data collection begins January 1, 2028 for lenders meeting the 2026–2027 threshold; first reporting filing due June 1, 2029. Any compliant SMB lending platform must support structured data capture, firewall controls, and HMDA-style LAR (Loan Application Register) export.

**SBA SOP 50 10 — SBA Loan Program Standard Operating Procedures**
- Official URL: https://www.sba.gov/document/sop--50-10-lender-development-company-loan-programs
- Governing standard operating procedures for SBA 7(a), 504, and SBA Express loan programs. Defines eligibility criteria, credit standards, use-of-proceeds rules, loan structuring requirements, and collateral policies. Compliance is mandatory for SBA-approved lenders. The SBA publishes updates periodically; SOP 50 10 7 is the current edition.

**Bank Secrecy Act (BSA) / Anti-Money Laundering (AML) — FinCEN**
- Official URL: https://www.fincen.gov/resources/statutes-and-regulations/bank-secrecy-act
- Requires financial institutions involved in lending to maintain AML programs, file Suspicious Activity Reports (SARs), and conduct Customer Due Diligence (CDD) and Know Your Customer (KYC) checks on all borrowers. SMB lending platforms must integrate or interface with BSA/AML compliance workflows at origination.

**HMDA — Home Mortgage Disclosure Act**
- Official URL: https://www.consumerfinance.gov/data-research/hmda/
- Applies to SMB lending where real estate is used as collateral. Mandates demographic reporting on applicants and loan terms. The CFPB HMDA Platform API allows submitters to upload LAR data programmatically: https://ffiec.cfpb.gov/documentation/2024/submission-api/

**Equal Credit Opportunity Act (ECOA) / Regulation B**
- Official URL: https://www.consumerfinance.gov/rules-policy/regulations/1002/
- Prohibits discriminatory lending decisions. SMB lending platforms using AI/ML decisioning models must maintain audit trails and model fairness documentation to demonstrate ECOA compliance; relates directly to the Section 1071 data collection regime.

---

### ISO Standards

**ISO 20022 — Universal Financial Industry Message Scheme**
- Official URL: https://www.iso20022.org/iso-20022
- Message Definitions: https://www.iso20022.org/iso-20022-message-definitions
- APIs and ISO 20022: https://www.iso20022.org/about-iso-20022/apis-and-iso-20022
- The dominant international standard for financial messaging. Governs payment initiation, clearing and settlement, cash management, and account management messages in JSON and XML. Relevant to loan disbursement and repayment payment flows; SWIFT's migration to ISO 20022 completed October 2025. SMB lending platforms must support ISO 20022 pacs (payment clearing) and camt (cash management) message sets for interoperability with bank rails.

**ISO 27001 — Information Security Management Systems**
- Official URL: https://www.iso.org/standard/27001
- The global benchmark for information security. Fintech lending platforms processing sensitive borrower financial and identity data are expected to hold ISO 27001 certification or equivalent (SOC 2 Type II). Defines requirements for risk management, access controls, incident response, and security operations.

**ISO 31000 — Risk Management**
- Official URL: https://www.iso.org/standard/65694.html
- Provides principles and guidelines for risk management applicable to credit risk frameworks within lending platforms. Relevant to documenting and governing AI/ML underwriting model risk.

---

### W3C & IETF Standards

**RFC 6749 — The OAuth 2.0 Authorization Framework**
- Official URL: https://datatracker.ietf.org/doc/html/rfc6749
- Foundational authorization standard for API access delegation. Required for all lending platform APIs that allow third parties (brokers, embedded finance partners, accounting software) to access data on behalf of users.

**RFC 7519 — JSON Web Token (JWT)**
- Official URL: https://datatracker.ietf.org/doc/html/rfc7519
- Standard format for securely transmitting claims between parties as a JSON object. Used in lending API authentication tokens, session management, and signed loan document assertions.

**RFC 8705 — OAuth 2.0 Mutual-TLS Client Authentication and Certificate-Bound Access Tokens**
- Official URL: https://datatracker.ietf.org/doc/html/rfc8705
- Binds OAuth 2.0 access tokens to TLS client certificates (mTLS), preventing token theft attacks. Required by FAPI 2.0 for high-security financial API deployments. Particularly important for machine-to-machine integrations between lending platforms and bank systems.

**RFC 7231 — Hypertext Transfer Protocol (HTTP/1.1) Semantics and Content**
- Official URL: https://datatracker.ietf.org/doc/html/rfc7231
- Defines HTTP method semantics (GET, POST, PUT, PATCH, DELETE) and status codes. The foundational standard for RESTful lending API design.

---

### Data Model & API Specifications

**OpenAPI Specification 3.1.1**
- Official URL: https://spec.openapis.org/oas/v3.1.1.html
- OpenAPI Initiative: https://www.openapis.org/
- The industry-standard format for describing RESTful APIs in YAML or JSON. Lending platforms should publish OpenAPI 3.1 specs for all public and partner-facing APIs. OAS 3.1 introduces full JSON Schema Draft 2020-12 compatibility, supporting complex financial data models including conditional validation and strict type enforcement.

**MISMO — Mortgage Industry Standards Maintenance Organisation**
- Official URL: https://www.mismo.org/
- MISMO APIs: https://www.mismo.org/standards-resources/apis
- Commercial Specifications: https://www.mismo.org/standards-resources/commercial-specifications
- MISMO provides the data dictionary and logical data model for real-estate-secured lending. The Commercial Reference Model covers commercial mortgage origination, servicing, secondary market, and real estate services. MISMO Version 3.4+ includes API toolkit standards. Mandatory for SMB loans secured by commercial real estate.

**JSON Schema Draft 2020-12**
- Official URL: https://json-schema.org/specification
- Used in conjunction with OpenAPI 3.1 for validating loan application payloads, financial data submissions, and API request/response objects. Supports the complex conditional and cross-field validation logic required in lending data models.

---

### Security & Authentication Standards

**FAPI 2.0 — Financial-grade API Security Profile**
- Official URL: https://openid.net/specs/fapi-security-profile-2_0-final.html
- FAPI Working Group: https://openid.net/wg/fapi/
- FAPI 1.0 Baseline: https://openid.net/specs/openid-financial-api-part-1-1_0.html
- FAPI 1.0 Advanced: https://openid.net/specs/openid-financial-api-part-2-1_0.html
- The OpenID Foundation's Financial-grade API profile specifies security requirements beyond standard OAuth 2.0 for high-value financial transactions. FAPI 2.0 mandates mTLS (RFC 8705), Pushed Authorisation Requests (PAR), and DPoP (Demonstrating Proof-of-Possession). The UK Open Banking Standard v4.0 is aligned with FAPI 1.0 Advanced. Lending platforms serving regulated financial institutions should implement FAPI 2.0 for their partner-facing APIs.

**OWASP API Security Top 10 (2023)**
- Official URL: https://owasp.org/API-Security/
- The authoritative checklist of critical API security vulnerabilities. The top risks for lending platforms are: Broken Object Level Authorization (BOLA — prevent cross-borrower data access), Broken Authentication (enforce MFA and short-lived tokens), Broken Object Property Level Authorization (restrict field-level access to PII and financial data), Unrestricted Resource Consumption (rate-limit credit bureau and underwriting calls), and Server Side Request Forgery (validate webhook and callback URLs).

**GDPR (General Data Protection Regulation) / CCPA (California Consumer Privacy Act)**
- GDPR: https://gdpr-info.eu/
- CCPA: https://oag.ca.gov/privacy/ccpa
- Data privacy frameworks governing collection, storage, processing, and deletion of borrower personal and financial data. Lending platforms must implement consent management, data minimisation, right-to-erasure workflows, and data residency controls.

---

### Open Banking & Data Access Standards

**UK Open Banking Standard v4.0**
- Official URL: https://standards.openbanking.org.uk/
- Open Banking UK: https://www.openbanking.org.uk/
- Provides Read/Write API specifications (AISP and PISP), security profiles aligned with FAPI 1.0 Advanced, and customer experience guidelines. As of Q2 2025, 13.3 million active UK open banking users with 31 million payments per month. Directly applicable for UK-market SMB lending platforms accessing borrower bank account data for cash-flow underwriting.

**PSD2 — EU Payment Services Directive 2**
- Official URL: https://ec.europa.eu/info/law/payment-services-psd-2-directive-eu-2015-2366_en
- Mandates open access to payment account data via APIs for authorised Third Party Providers (TPPs) across the EU. Enables SMB lending platforms to access applicant bank transaction data for underwriting with user consent, without requiring screen scraping.

---

### SBA Technical Specifications

**SBA ETRAN API v9.2**
- API Documentation: https://catweb.sba.gov/apidocs/elend.cfm
- XSD Schemas (Origination): https://catweb2.sba.gov/elend/etranshared/SBA_ETran.curr.orig.xsd
- The SBA's Electronic Loan Origination and Reporting system. Provides web service methods for loan guarantee submission: Originate3, Originate4, OrigScore, OrigUpdate, and Underwriting. Current version 9.2 XSD schemas published September 2025. The OrigBypass function is decommissioned from March 1, 2026; OrigScore continues. Any SBA-authorised lender platform must integrate with ETRAN for guarantee submissions.

---

## Similar Products — Developer Documentation & APIs

### Mambu
- **Description:** Cloud-native composable banking platform offering modular APIs for loan origination, underwriting, servicing, and collections. Used by fintechs, digital banks, and credit unions.
- **API Documentation:** https://docs.mambu.com/api/
- **API v2 Welcome:** https://docs.mambu.com/api/pages/api-v2/welcome/
- **SDKs/Libraries:** REST API with language bindings in cURL, JavaScript, Node.js, Ruby, Python, Java, Go
- **Developer Guide:** https://support.mambu.com/docs/mambu-apis
- **Standards:** REST/JSON, OpenAPI; JSON/YAML response format
- **Authentication:** OAuth 2.0; API key for sandbox

### nCino
- **Description:** Cloud banking operating system built on Salesforce, covering CRM-integrated loan origination, underwriting, document management, portfolio monitoring, and compliance for community banks and credit unions.
- **API Documentation:** https://developer.ncino.com/
- **SDKs/Libraries:** Salesforce Apex, REST/JSON via Salesforce Connected Apps
- **Developer Guide:** https://developer.ncino.com/ (requires registration)
- **Standards:** REST/JSON via Salesforce platform; Salesforce SOQL/Apex
- **Authentication:** Salesforce OAuth 2.0

### TurnKey Lender
- **Description:** AI-powered all-in-one lending platform for origination, underwriting, servicing, and collections, operating in 50+ countries with sub-30-second decisioning.
- **API Documentation:** https://turnkey-lender-api.readme.io/reference/welcome-to-turnkey-lender-api
- **Integrations Overview:** https://www.turnkey-lender.com/lending-platform-api-integrations/
- **Developer Guide:** https://turnkey-lender-api.readme.io/ (live demo sandbox available)
- **Standards:** REST/JSON; webhook event notifications
- **Authentication:** API key; OAuth 2.0 for partner integrations

### Lendflow
- **Description:** Embedded credit infrastructure (API-first) enabling vertical SaaS platforms to offer SMB lending natively; covers pre-qualification, origination, and decisioning workflows.
- **API Documentation:** https://app.lendflow.io/docs/ and https://api.lendflow.com/docs
- **Developer Resources:** https://www.lendflow.com/resources/developers
- **SDKs/Libraries:** REST API; Bearer token authentication
- **Standards:** REST/JSON; OpenAPI; webhook event-driven notifications
- **Authentication:** Bearer Token (API key issued via client portal)

### Stripe Capital
- **Description:** Embedded business financing for Stripe Connect platforms; offers cash advances and loans to connected accounts based on Stripe payment processing history.
- **API Documentation:** https://docs.stripe.com/capital/overview
- **API Integration Guide:** https://docs.stripe.com/capital/api-integration
- **Embedded Components:** https://docs.stripe.com/connect/supported-embedded-components/capital-financing
- **SDKs/Libraries:** Stripe SDKs (JavaScript, Python, Ruby, PHP, Go, Java, .NET, iOS, Android)
- **Standards:** REST/JSON; OpenAPI; Stripe-flavoured event webhooks
- **Authentication:** Stripe API keys; OAuth 2.0 for Connect platforms

### Plaid
- **Description:** Financial data infrastructure connecting to 12,000+ financial institutions. Plaid Check provides structured cash-flow data for lending underwriting, including 24-month transaction history, income verification, and balance data.
- **API Documentation:** https://plaid.com/docs/api/
- **Cash Flow Underwriting:** https://plaid.com/check/underwriting/
- **SDKs/Libraries:** JavaScript, React, iOS, Android, Python, Node.js, Ruby, Go
- **Developer Guide:** https://plaid.com/docs/
- **Standards:** REST/JSON; OAuth-based account linking (Link flow); OpenAPI spec published
- **Authentication:** client_id + secret (server-side); Link token flow for end-user consent; Plaid is a CFPB-recognised consumer reporting agency (CRA) for cash-flow data

### Experian — Business Information APIs
- **Description:** Commercial credit bureau providing business credit reports, Intelliscore Plus commercial scores, blended consumer/commercial scores for small businesses, and identity verification.
- **API Documentation:** https://developer.experian.com
- **API Hub:** https://www.experian.com/business-information/api-hub
- **Standards:** REST/JSON; OpenAPI
- **Authentication:** OAuth 2.0; API key for sandbox

### Equifax — Small Business Credit APIs
- **Description:** Credit bureau providing business credit reports, commercial scores, and credit monitoring APIs. The Equifax Developer Portal covers consumer and commercial credit access.
- **API Documentation:** https://developer.equifax.com/
- **Credit Reports API:** https://developer.equifax.com/products/apiproducts/credit-reports
- **SDKs/Libraries:** REST/JSON; language-agnostic
- **Standards:** REST/JSON; OpenAPI
- **Authentication:** OAuth 2.0 client credentials

### Codat
- **Description:** Unified API for accessing accounting, banking, and commerce financial data from 30+ platforms (QuickBooks, Xero, Sage, NetSuite, FreshBooks). Used by lending fintechs to pull SMB financial statements for underwriting without direct accounting software integrations.
- **API Documentation:** https://docs.codat.io/
- **Accounting Integrations Overview:** https://docs.codat.io/integrations/accounting/overview
- **Fintech Use Cases:** https://codat.io/industries/fintech/
- **SDKs/Libraries:** REST/JSON; SDKs for Python, Node.js, Java, C#
- **Standards:** REST/JSON; OpenAPI 3.0; webhooks
- **Authentication:** OAuth 2.0 (Codat manages upstream auth with each accounting platform); API key for platform-level access

---

## Notes

**Emerging Standards**

- **Consumer Financial Data Rights (CFPB Open Banking Rule, 2025):** The CFPB's Personal Financial Data Rights rule under Section 1033 of Dodd-Frank mandates US financial institutions to make consumer financial data available via APIs by late 2026 for the largest institutions. This will expand open banking data access for SMB lending underwriting in the US, similar to UK PSD2/Open Banking. Specifications are being coordinated through the Financial Data Exchange (FDX API): https://financialdataexchange.org/

- **FDX API Standard:** https://financialdataexchange.org/fdx/resources/fdx-api
  The Financial Data Exchange API is the emerging US open banking data standard, covering account, transaction, statement, tax, and investment data. Expected to become the de facto standard for US open banking data access as CFPB Section 1033 takes effect. Relevant for SMB lending platforms building cash-flow underwriting capabilities.

- **Model Risk Management (SR 11-7 / OCC Guidance):** Federal Reserve SR 11-7 and OCC guidance on model risk management apply to AI/ML underwriting models used by bank-affiliated lenders. Platforms must support model documentation, validation, and governance reporting workflows. Official guidance: https://www.federalreserve.gov/supervisionreg/srletters/sr1107.htm

- **Fair Lending / ECOA Model Fairness:** The CFPB and OCC expect lenders using algorithmic underwriting to produce adverse action notices that are specific to the factors contributing to a decline — "model explainability" is a de facto regulatory expectation even without a formal standard. Tools such as SHAP (SHapley Additive exPlanations) values are the practical implementation approach.

**Gaps**

No single published ISO standard governs end-to-end SMB loan origination data models (unlike residential mortgage where MISMO fills this role). The MISMO Commercial Reference Model is the closest available standard for real-estate-secured commercial transactions, but its adoption in pure SMB cash-flow lending is limited. This gap represents an opportunity for open-source data model standardisation.
