# Account Reconciliation  
**Retired the previous platform and implemented an automated Alteryx workflow to perform the key control function**

---

## Project Background
A core system used daily to track cash and securities in house accounts was decommissioned with one month’s notice. The system served as a critical operational control, supported management reviews, and was subject to regular audits. Limited cross‑team communication during the transition created immediate operational and audit risk. The team needed a fast, reliable replacement that preserved control integrity and fit seamlessly into the morning workflow without adding manual effort.

**Key factors**
- **Critical daily control**  
- **One‑month shutdown notice**  
- **Limited cross‑team communication**  
- **Operational and audit risk**

---

## Data Structure

---

## Executive Summary
We replaced the retired platform with an automated Alteryx workflow combined with SQL validation to restore and improve the daily house‑account reconciliation control. The solution ingests redacted extracts, applies cleaning and reconciliation logic, validates results against SQL transaction data, and produces an audit‑ready Excel report automatically at the start of day. The new process preserves control effectiveness, reduces manual effort, and delivers earlier visibility for downstream teams.

**Primary outcomes**
- **Report available at start of day** (previously delayed by hours)  
- **Stronger daily controls** via automated validation and standardized evidence  
- **Reduced operational bottlenecks** and improved management visibility  
- **Foundation for further automation and documentation improvements**

---

## Insights Deep Dive
**Discovery and issue logging**  
Early review of account outputs surfaced anomalies (for example, mismatched security identifiers in a subset of accounts). Documenting these issues up front allowed fixes to be encoded into the workflow logic rather than patched later.

**SQL validation and sampling strategy**  
Given the one‑month timeline, we validated the workflow on a representative sample (2–3 accounts per team) to cover different account types and edge cases. Cross‑checking Alteryx outputs with SQL transaction data confirmed completeness and accuracy before full rollout.

**Workflow design and automation**  
The Alteryx workflow is modular: ingestion → cleaning → reconciliation → exception handling → export. It runs automatically at start of day, produces the standardized Excel report, and generates audit evidence for management and auditors.

**Operational integration**  
Design prioritized zero additional morning steps for end users. Documentation and quick reference guides were created and training sessions delivered to ensure smooth adoption.

---

## Recommendations
- **Expand automated exception handling** to capture additional edge cases discovered during scaling.  
- **Add CI checks** for SQL scripts and workflow exports to prevent regressions when updating logic.  
- **Schedule periodic reconciliation tests** and snapshot audit evidence for ongoing assurance.  
- **Document configuration templates** and use environment variables or secure vaults for credentials; never store secrets in the repo.  
- **Iterate toward dashboarding** for near‑real‑time monitoring and to surface trends that can reduce recurring exceptions.

---

## Workflow Image
Add a redacted visual of the Alteryx workflow to this page. Example markdown:

```markdown
![Alteryx workflow diagram](/assets/workflow-diagram.png "Alteryx workflow diagram — redacted")
