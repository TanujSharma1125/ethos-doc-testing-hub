# Insurance & Ethos Glossary

Reference for QA testers with no insurance background. Terms are organized by category.

---

## Product & Policy Terms

**ADB (Accelerated Death Benefit)**
A rider attached to a life insurance policy that allows the insured to receive a portion of the death benefit early if diagnosed with a terminal illness. LGA Prime includes an ADB rider in every policy packet.

**Amendment to Application**
A supplemental form (LU-14(54-62)) added to the application packet when a policy goes through RUW (rated underwriting). It documents any changes made to the original application during underwriting.

**Beneficiary**
The person or entity designated to receive the death benefit when the insured dies. Captured in Section II of the application (ICC19-ETH).

**Buyer's Guide**
A carrier-agnostic informational document (not signed) that explains how life insurance works. Required to be appended to the application packet in all states. State-specific versions exist for ME and NJ.

**Death Benefit**
The amount of money paid to the beneficiary when the insured person dies. Also called the face amount or coverage amount.

**EFT (Electronic Funds Transfer)**
Automatic bank debit used to pay insurance premiums. The insured authorizes this in the Declarations section of the application.

**Face Amount**
The dollar amount of life insurance coverage applied for (e.g., $500,000). Shown in Section V of the application.

**In-Force**
A policy is "in-force" (active) when: (1) the policy has been delivered and accepted, (2) the full first premium has been paid, and (3) there has been no change in the insured's health or habits since the application.

**Insured**
The person whose life is covered by the insurance policy. Also called the "Proposed Insured" on the application.

**Modal Premium**
The premium amount for a given payment frequency (monthly, quarterly, semi-annual, annual). Calculated from the product rate table based on age, gender, tobacco use, risk class, state, and face amount.

**Owner**
The person or entity that owns the policy. Often the same as the insured, but can be different (e.g., a spouse or trust). Has the right to make changes to the policy.

**Payor**
The person or entity responsible for paying the premiums. Usually the same as the owner.

**Perks Rider / Perks Benefit**
An Ethos-specific benefit included with LGA Prime policies. The Perks Rider (ICC21-ETHLP) is included in all states; the Perks Benefit (21-ETH PERKS) is an additional form included only for CA and FL.

**Policy Contract**
The legal document that constitutes the insurance policy. For LGA Prime, this consists of multiple sections: Part 1 (ICC23-P or ICC24-P2), Schedule Sections 1–4, Part 2, and Back Cover.

**Policy Effective Date**
The date the insurance coverage begins. For LGA Prime, this is the date the policy is delivered and accepted AND the first premium is paid while the insured is alive.

**Premium**
The amount paid by the insured (or payor) to keep the policy active. Computed fresh from the product rate table — never hardcoded in QA tests.

**Risk Class**
The underwriting category assigned to the insured based on their health profile. Common classes: Preferred Plus Non-Tobacco, Preferred Non-Tobacco, Standard Non-Tobacco, Preferred Tobacco, Standard Tobacco. Affects premium.

**Rider**
An add-on to the base insurance policy that provides additional coverage or benefits. LGA Prime includes the ADB Rider and Perks Rider.

**Term Life Insurance**
Life insurance that covers the insured for a fixed period (term). LGA Prime offers 10, 15, 20, 25, 30, 35, and 40-year terms. No cash value; pays only if the insured dies during the term.

---

## Forms & Documents Terms

**Application**
The form completed by the applicant to apply for life insurance. For LGA Prime: ICC19-ETH (compact/standard), with state-specific variants for CA, ND, DE, SD, and FL.

**Auth Packet / Authorization Packet**
The set of forms signed before the application. Includes e-sign consent, HIPAA, FCRA, MIB notice, phone/SMS consent, and notice of insurance practices. Always the first forms presented in DocuSign.

**Compact States**
States that accept the standard ICC (Interstate Compact) form numbers rather than requiring state-specific form filings. For LGA Prime: most US states except CA, DE, FL, ND, SD, SC (which have their own contract pages).

**Doc Control / External Doc Control**
An internal reference number used to track and manage form versions in the PCS system.

**DocuSign Envelope**
A DocuSign container holding all the documents for a single signing session. Each test run should capture the envelope ID for the M&T log.

**Endorsement**
A modification to the policy contract that changes specific terms for a particular state. LGA Prime has state endorsements for KS, ME, MO, PA, VA, and WY.

**Filed Form Number**
The form number registered with the state insurance department. May differ from the internal form number.

**Form Control**
A configuration entity in PCS that groups forms together for a specific product/channel. LGA Prime uses: LGA_Reprice_Prime, LGA_Price_Elasticity_Prime, Agnostic_Replacements_DTC, Agnostic_Replacements_AA, and Life.

**Form Key / UUID**
A unique identifier for each form in the DocuSign system. Used to reference forms in the PCS JSON configuration.

**Form Version**
The version number of the form. Carrier-approved forms must use the correct version — older versions may not be filed or approved.

**Guarantee Association Notice (GAN)**
A state-required notice informing policyholders of the protections provided by their state's life and health insurance guaranty association. Included in the policy packet for states that require it. Form numbers: 21-ETH GAN [STATE].

**ICC (Interstate Insurance Product Regulation Compact)**
A multi-state regulatory compact that allows carriers to file one form for approval across multiple member states. ICC form numbers are accepted in "compact" states.

**Policy Packet**
The set of documents delivered to the insured after underwriting approval. Includes the policy contract, riders, disclosures, delivery receipt, and state endorsements.

**SOH (Statement of Good Health)**
A form (ICC14-LU1013) signed by the applicant confirming their health has not changed since the application. Included in the policy packet.

---

## Underwriting Terms

**MIB (Medical Information Bureau)**
A cooperative data exchange used by insurance companies to share information about past insurance applications. The MIB Notice (24-ETH MIBN) authorizes MIB to share information about the applicant.

**RUW (Rated/Underwritten Policy)**
A policy that requires manual underwriting review (as opposed to straight-through automated approval). RUW policies require the Amendment to Application (LU-14(54-62)) to be included.

**Straight-Through / STP**
A policy application that is approved automatically without manual underwriter review. No Amendment to Application is triggered.

**Underwriting**
The process of evaluating an insurance application to determine whether to offer coverage and at what rate. Involves reviewing medical history, financial information, and other risk factors.

---

## Regulatory & Compliance Terms

**FCRA (Fair Credit Reporting Act)**
Federal law governing how consumer credit information is used. The FCRA Consumer Report Authorization (22-ETH FRCA) is required in the auth packet.

**HIPAA (Health Insurance Portability and Accountability Act)**
Federal law governing the privacy and security of health information. Two HIPAA forms are required:
1. **25-ETH HIPAA RTA** — Ethos-branded, always in auth packet (signed by insured)
2. **ICC20 LU-1250** — Banner Life-branded, always in application packet (signed by insured + agent/witness)

**Legal Center**
Ethos's internal compliance repository where carrier-agnostic form versions are stored and approved. Auth forms must match the Legal Center version.

**M&T (Monitoring & Testing)**
The quarterly compliance process of running standardized test policies and documenting results. Required by the Compliance SOP for LGA Prime, Ameritas Choice, IUL, Protective, and TruStage products.

**NAIC (National Association of Insurance Commissioners)**
The US standard-setting organization for insurance regulation. The NAIC Buyer's Guide is a standardized document format.

**Replacement**
When a new insurance policy is purchased with the intent to lapse, surrender, or otherwise reduce an existing life insurance policy. Triggers state-specific replacement disclosure forms.

**RTA (Release Transfer Authorization)**
Authorizes Ethos to use the insured's HIPAA signature to sign other carrier-specific medical release forms on the insured's behalf. Form: 25-ETH RTA v.2.

---

## Channel Terms

**DTC (Direct-to-Consumer)**
The online application flow where the customer completes the application themselves without an agent. Uses Agnostic_Replacements_DTC form control for replacement forms.

**AA (Agent-Assisted)**
The application flow where a licensed agent completes the application on behalf of the customer. Uses Agnostic_Replacements_AA form control. Replacement trigger rules differ slightly from DTC.

**Funnel**
The online application interview flow (interview funnel) that collects applicant responses. Field values in the funnel are the source of truth for all application form fields — QA must verify each field against actual funnel responses.

**AskLabel**
The internal identifier for a specific question in the interview funnel. Used in business rules to trigger forms (e.g., `replacing-existing-insurance` AskLabel triggers replacement forms).

---

## PCS (Product Configuration System) Terms

**PCS**
Product Configuration System — the internal system that stores all form configurations, business rules, DocuSign field mappings, and product settings for Ethos insurance products.

**Form Control**
A named configuration in PCS that defines which forms are included for a given product/channel combination. See the Form Control sheet in the PCS Excel file.

**Business Rule**
A condition in PCS that determines when a form is triggered or suppressed. Examples: "Include for RUW Policies", "If AskLabel replacing-existing-insurance = yes".

**Auth Combined / Application Combined / Policy Combined**
PCS columns indicating which packet a form belongs to: Y = included in that packet, N = not included.

**Form Status**
The lifecycle status of a form in PCS:
- **Pending** = active, being configured (treated same as Active for testing)
- **Implemented** = active, fully configured and in production
- **New** = newly added, not yet active
- **Obsolete** = retired, must NOT be tested or included in checklists
- **Legacy** = old form control (LGA_ER_DTC_v1/v2) — do not use for current testing

**Compact State List**
The list of states for a given form control that use ICC/compact form numbers rather than state-specific filings. Defined in the Form Control sheet.

**Start Date / End Date**
Dates controlling when a form is active. Forms with an End Date in the past should not be tested unless explicitly noted.
