# SMB Lending Platform

> Part of the [worlds-biggest-software-project](https://github.com/worlds-biggest-software-project) initiative.
>
> An AI-native, open-source platform for small business loan application, credit decisioning, and servicing.

The SMB Lending Platform is an end-to-end loan lifecycle system covering origination, underwriting, servicing, and collections for small and medium-sized businesses. It targets community banks, credit unions, fintech lenders, SBA-approved lenders, and B2B platforms embedding credit offerings — providing a modern, standards-aligned alternative to expensive, proprietary incumbents.

---

## Why SMB Lending Platform?

- Incumbent platforms such as nCino, Mambu, and TurnKey Lender are priced for enterprise budgets — typically $100,000–$500,000/year in licensing — putting them out of reach for smaller lenders and embedded-finance startups.
- nCino's dominant position in community banks comes with a hard Salesforce dependency, increasing total cost of ownership and limiting flexibility for non-standard lending products.
- Decisioning specialists like JUDI.AI and origination-only tools like Lendflow force lenders to stitch together multiple proprietary stacks rather than offering a coherent end-to-end platform.
- Dodd-Frank Section 1071 demographic and pricing data collection is now a major operational burden for any lender originating 100+ SMB loans annually, and tooling is uneven across vendors.
- No serious open-source alternative exists in a $2.5T (2023) market projected to reach $7.2T by 2032, leaving lenders without an auditable, self-hostable foundation for credit decisioning models.

---

## Key Features

### Loan Origination & Application

- Digital loan application submission with e-signature
- Borrower portal with loan status and payment history
- White-label borrower experience for embedded finance partners
- Loan officer mobile application
- REST APIs for third-party and embedded integrations

### Underwriting & Decisioning

- Underwriting workflow with approval routing and history
- Credit decisioning engine (rules-based or ML-powered)
- Cash-flow-based underwriting using bank transaction data
- Automated document spreading from tax returns, bank statements, and P&Ls
- Credit bureau integration for credit scores and fraud flags

### Servicing & Collections

- Payment collection, statement generation, and escrow management
- Payment processing with multiple funding sources
- Collections workflow with delinquency escalation rules
- Portfolio risk analytics dashboard
- Early warning system for delinquency

### Compliance, Risk & Fraud

- KYC/AML screening and compliance checks
- Regulatory compliance reporting (SBA SOP 50 10, Dodd-Frank Section 1071, HMDA where applicable)
- Fraud detection at origination (synthetic identity, altered documents)
- Audit trails for all transactions
- Auditable, model-level transparency for non-discriminatory lending

### Extensibility (Backlog)

- Composable/modular architecture for custom lending products
- No-code workflow builder for non-technical lenders
- Conversational AI for application assistance
- Post-disbursement borrower monitoring and covenant alerts
- Accounting software integrations (QuickBooks, Xero, Freshbooks)

---

## AI-Native Advantage

AI is applied where it directly reduces decision time, fraud loss, and manual analyst work: cash-flow-based credit models trained on bank transaction data underwrite SMBs that lack traditional credit history; document-spreading models extract structured financials from tax returns and bank statements in seconds rather than hours; anomaly-detection models flag synthetic identities and altered documents at origination; and post-disbursement agents monitor borrower transaction patterns to surface early warnings before covenants are breached. A natural-language application assistant guides SMB owners through eligibility, document collection, and form pre-population from connected accounting and POS data.

---

## Tech Stack & Deployment

The platform is designed API-first, mirroring modern incumbents like Mambu, LendFoundry, and Lendflow, with optional white-label borrower and loan-officer UIs. Expected deployment modes include self-hosted and cloud, with embedded-finance use cases supported through REST APIs and webhook events. Standards alignment includes SBA SOP 50 10, URLA / SBA Form 1919, Dodd-Frank Section 1071, HMDA, MISMO (for real-estate-secured SMB loans), ISO 20022 for payment messaging, and GDPR / CCPA for applicant data privacy. Integrations target credit bureaus, payment processors, KYC/AML providers, and core banking systems.

---

## Market Context

The global small business loans market was valued at $2.5 trillion in 2023 and is projected to reach $7.2 trillion by 2032 at a 13.0% CAGR (Allied Market Research, 2024). Embedded B2B lending is forecast to reach $50–75 billion in volume by 2026, roughly 15% of total SMB lending (Bain & Company, 2025). Software platform pricing ranges from $100,000–$500,000/year in enterprise licensing to $50–$200 per originated loan, with API-embedded models using revenue share or per-call pricing. Primary buyers are community banks and credit unions modernising SMB workflows, fintech lenders building automated underwriting, SBA-approved lenders, and B2B platforms embedding credit for their SMB customers.

---

## Project Status

> This project is in the **research and specification phase**.  
> Contributions, feedback, and domain expertise are welcome.

---

## Contributing

We welcome contributions from developers, domain experts, and potential users.
See [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines.

**Important:** All contributions must be your own original work or clearly attributed
open-source material with a compatible licence. Copyright infringement and licence
violations will not be tolerated and will result in immediate removal of the offending
contribution. If you are unsure whether a piece of code, text, or other material is
safe to contribute, open an issue and ask before submitting.

---

## Licence

Licence to be determined. See [discussion](#) for context.
