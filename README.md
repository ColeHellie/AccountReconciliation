# Account Reconciliation  
**Retired the previous platform and implemented an automated Alteryx workflow to perform the key control function**

---

## Project Background
A core system used daily to track cash and securities in house accounts was decommissioned with one month’s notice. The system served as a critical operational control, supported management reviews, and was subject to regular audits. There was limited communication throughout the organization to properly prepare for the the transition and created immediate operational and audit risk. The team needed a fast, reliable replacement that preserved control integrity and fit seamlessly into the morning workflow without adding manual effort.

**Key factors**
- **Critical daily control**  
- **One‑month shutdown notice**  
- **Limited cross‑team communication**  
- **Operational and audit risk**

---

## Data Structure
The rebuilt process uses daily transaction extracts and a base Excel file that lists outstanding items. SQL is used to pull the transaction data. (Note: All data inputs had to be omitted)
- **Inputs:** SQL query to pull previous day’s transactions for all suspense accounts and a base Excel file that contained all previous outstanding items; the process adds the previous day’s transactions and collapses items when the balance is zero.  
- **Core fields:** account number, transaction date, age, amount ($), quantity (shares), security identifier, and control number.  
- **What we do:** Standardize the inputs, match transactions to outstanding items, and produce the same Excel report format used by the prior system.
---

## Executive Summary
Automated Alteryx workflow plus SQL validation that recreates the daily reconciliation report, strengthens controls, and speeds up morning reporting.

**Primary outcomes**
- **Report available at start of day** (previously delayed 2-3 Hours)  
- **Stronger daily controls** Potential to create dashboards and reports to highlight aged items 
- **Foundation for further automation and documentation improvements**

---

## Insights Deep Dive
**Discovery and issue logging**  
 During initial checks, I found that a subset of accounts did not display the security identifier, which required additional matching logic.

**SQL validation and sampling strategy**  
With only one month to deliver, we validated the workflow using a small, representative sample of accounts (2-3 accounts per team) to cover different account types and scenarios. We compared the Alteryx outputs to the typical morning reports produced by the prior system to confirm accuracy before rolling the solution out department‑wide.

**Workflow design and automation**  
The Alteryx workflow is modular: ingestion → cleaning → reconciliation → exception handling → export. It runs automatically at start of day, produces the standardized Excel reports which it then uses the following day.

**Operational integration**  
Design prioritized zero additional morning steps for end users. Documentation and quick reference guides were created and training sessions delivered to ensure smooth adoption.

---

## Recommendations for platform transition
- Build a simple dashboard - show high value and aged items.
- Update the training manual and schedule training sessions - document any changes and give quick refresh sessions for owners of suspense accounts.
- Automatically catch more exceptions - add rules so the workflow adapts to unusual cases.


