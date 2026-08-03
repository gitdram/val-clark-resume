# Recruiter Screening Notes

Notes from a chatbot recruiter screening prep session based on resume content in `index.html`.

---

## 1. Logic and reasoning to evaluate alternative solutions

**Question:** How would we rate experience with using logic and reasoning to identify the strengths and weaknesses of alternative solutions, conclusions, or approaches to problems?

### Recommended rating: **Extensive** (top tier on most 5-point scales)

If the scale is 1–5 (None → Limited → Some → Considerable → Extensive), **5 / Extensive** is well supported. If you need to be conservative, **4 / Considerable** is the floor — not lower.

### Why that rating fits

The resume shows this skill **repeatedly, at increasing seniority, with explicit decision-making language** — not just “I fixed things,” but “I evaluated options and chose a path.”

#### Direct evidence of comparing alternatives

| Example | What it demonstrates |
|--------|----------------------|
| Cisco Core Switch upgrade (Renown) | Explicit **pros/cons**, **model comparisons**, utilization trending, finance justification |
| QoS project (Renown) | **Weighted vendor analysis**, RFQ, **POC** across NetScout, Network Instruments, SolarWinds |
| Azure China Key Vault design (Nike) | Chose cross-region secret linking over **redundant China resources** — clear cost/architecture trade-off |
| Legacy AD sync → Azure Runbook (Nike) | Evaluated retire-on-prem vs. cloud automation |
| ScienceLogic → SolarWinds migration (Nike) | Tool/platform alternative evaluation |
| SNMP v2 → v3 (Nike) | Security vs. complexity trade-off |
| Multi-tenant → single-tenant Azure migration (Nike) | Subscription architecture decision as PM/Lead |
| AT&T invoice vs. network diagrams (NS Bank) | Analytical comparison leading to **cost-saving decommissioning** |

#### Sustained, senior-level use

Over **10+ years**, applied in:

- **Architecture & design** — IaC, API co-design, BlueCat-on-Azure, observability stack choices
- **Project leadership** — sprint planning, migrations, lead engineer roles
- **Standards & governance** — Wells Fargo Standards Task Force decisions
- **Vendor/tool selection** — formal RFQs, weighted scoring, POCs

#### Supporting background

**AA in Accounting** adds formal analytical training, which strengthens the narrative even though most evidence is from engineering work.

### Sample narrative (if there is a free-text box)

> For 10+ years I have routinely evaluated alternative technical approaches before implementation — documenting pros/cons, running weighted vendor analyses and POCs, and selecting solutions based on cost, security, operability, and scale. Examples include Azure China Key Vault architecture (avoiding redundant regional resources), BlueCat and subscription migration strategy at Nike, and formal vendor evaluation for network analysis tools at Renown Health.

### When to choose Considerable (4) instead

Use **4** only if:

- The form defines “Extensive” as daily primary duty for 5+ years in your **current** title only, or
- You want to stay conservative because many bullets describe execution more than documented trade-off analysis.

Even then, the Renown and Nike lead/architect bullets give strong grounds for **5**.

### Quick self-check against typical scale definitions

| Level | Does the resume support it? |
|-------|------------------------------|
| **None / Limited** | No — too much counter-evidence |
| **Some** | Undersells; far more than occasional use |
| **Considerable** | Minimum reasonable rating |
| **Extensive** | Best fit — recurring lead/architect decisions with documented comparison of alternatives |

---

## 2. Azure Policy at scale

**Question:** Have you implemented and enforced Azure Policy at scale in enterprise environments?

### What “Azure Policy” means (specific product)

**Azure Policy** is a specific Azure governance service — not a generic phrase for “having policies in Azure.”

It lets an organization define **rules** (policy definitions) and assign them at **management group, subscription, or resource group** scope. Azure then **evaluates** resources against those rules and can:

- **Audit** — flag non-compliant resources (e.g., “storage accounts must use HTTPS”)
- **Deny** — block non-compliant creates/updates at the ARM API level
- **DeployIfNotExists / Modify** — auto-remediate or patch configuration
- Use **initiatives** — bundled policy sets (e.g., CIS benchmark, HIPAA-style controls)

“At scale in enterprise” usually means:

- Assigning policies across **many subscriptions** (often via management groups)
- Custom policy definitions + initiatives
- **Compliance dashboards** and remediation tasks
- Integration with **Landing Zone / CAF** governance
- Exemptions, policy versioning, and coordination with platform/security teams

### Not the same as

| Often confused with | Difference |
|---------------------|------------|
| **ARM templates / IaC** | Enforces at deploy time in *your* pipeline; Azure Policy enforces org-wide regardless of who deploys |
| **NSG rules** | Network firewall rules — not Azure Policy (though a policy *can require* NSGs) |
| **RBAC** | Who can do what — not what resources are allowed to look like |
| **Azure DevOps approvals / pipelines** | Process control, not native Azure resource governance |
| **Group Policy (Windows AD)** | On-prem Windows — different product |
| **SolarWinds “Compliance Policies”** | Config compliance in SolarWinds NCM, not Azure Policy |

### What the resume shows

Strong Azure platform work (IaC, ARM, Key Vault, subscription migration, NSGs, DevOps pipelines, etc.) but **no explicit mention of Azure Policy** — no assignments, custom definitions, initiatives, compliance reporting, or remediation at the Azure Policy layer.

### Recommended chatbot answer: **No**

Unless there is unstated Azure Policy work (e.g., at Nike under a platform team), do not click **Yes**. Mis-clicking often leads to a deeper screen asking for specifics.

**Related governance at scale (honest to claim):**

- Standards enforced via **ARM templates + param files + DevOps pipelines**
- **NSG rules/flow logs**, Key Vault secret patterns, subscription architecture (multi- → single-tenant)
- Enterprise **compliance/standards** experience (Wells Fargo Standards Task Force, SolarWinds compliance policies, etc.)

### If there is a “Limited” or free-text option

> No direct hands-on ownership of Azure Policy definitions/initiatives at enterprise scale. Extensive Azure governance via IaC (ARM), DevOps pipelines, Key Vault patterns, NSG standards, and large-scale subscription/resource migrations in a global enterprise.

### Self-check before saying Yes

You’d want to be able to answer “yes” to several of these:

1. Did you **author or assign** policy definitions or initiatives?
2. Did you use the **Compliance** blade or export compliance data?
3. Did you handle **exemptions**, **remediation tasks**, or **DeployIfNotExists** policies?
4. Was it across **multiple subscriptions / management groups**?

If those aren’t true, **No** is the right answer.

---

## 3. Cloud security, compliance, and regulated workloads (PHI/PII)

**Question:** Have you supported cloud environments with security, compliance, or regulated workloads (PHI/PII)?

### What the question is asking

They want to know if you’ve worked where:

1. **Cloud** (Azure/AWS/etc.) is in production, and
2. **Security/compliance matters** because data is sensitive or regulated — especially **PHI** (health info, HIPAA) or **PII** (personal/financial data).

“Supported” is broad: operating, securing, monitoring, or automating in those environments counts.

### What the resume supports

#### Regulated / PHI / PII experience — **strong yes**

| Employer | Regulated context |
|----------|-------------------|
| **Providence Health** | Healthcare — PHI/HIPAA environment |
| **Renown Health** | Healthcare — PHI/HIPAA environment |
| **Alere Medical** | Medical — regulated health data |
| **Wells Fargo** | Banking — PII; Client Security Compliance, BCP, Standards Task Force |
| **Nevada Security Bank** | Banking — compliance policies, audit-style operations |

#### Cloud + security — **strong yes**

At **Nike**, Azure work includes patterns that matter in regulated cloud:

- Key Vault for secrets (SSH keys, env vars, webhooks)
- OAuth/Okta for API access
- NSG rules and flow logs
- Enterprise-scale IaC, subscription migration, observability
- SNMP v3, credential standardization, alerting

#### Cloud + PHI/PII together — **partially explicit**

The resume does **not** say PHI/PII was handled **in Azure** (e.g., “HIPAA-compliant Azure landing zone”). Healthcare roles read as **on-prem network/monitoring** (pre–heavy cloud). Nike cloud work reads as **enterprise platform**, not labeled HIPAA/PII.

- **Strict reading:** regulated industry yes; cloud security yes; **documented cloud+PHI/PII same role** — weaker
- **Typical recruiter screening:** still a **Yes**

### Recommended chatbot answer: **Yes**

Enough combined evidence for a screening “Yes,” especially if there’s no “Limited” option.

If there’s **Limited / Some / Extensive**:

- **Some to Considerable** if they mean hands-on HIPAA cloud architect
- **Yes / Considerable** for general “supported regulated + cloud security” screening

### Follow-up talking points

**Short version:**

> Yes. I’ve worked in healthcare (Providence, Renown, Alere) and banking (Wells Fargo, Nevada Security Bank) with compliance and security requirements, and at Nike I’ve operated and automated Azure at enterprise scale with Key Vault, OAuth/Okta, NSG controls, and secure IaC/deployment patterns.

**If they push on PHI/PII in cloud specifically:**

> My direct PHI exposure was in healthcare network and monitoring environments; my cloud work at Nike is enterprise Azure with strong security and identity controls. I’m familiar with applying compliance-minded patterns — secrets management, access control, audit/logging, and standardized deployments — in large-scale cloud platforms.

Do not claim HIPAA cloud ownership unless a role actually involved HIPAA workloads in Azure.

### Honesty check before “Yes”

Answer **Yes** if you can discuss at least one of:

- Healthcare or banking compliance constraints you worked under
- Cloud security controls you implemented (Key Vault, OAuth, NSG, etc.)
- How you treated sensitive data (credentials, access, monitoring, change control)

Answer **No** only if experience were purely non-regulated cloud with no security/compliance angle — that is not this profile.

---

## Summary cheat sheet

| Screening question | Recommended answer |
|--------------------|-------------------|
| Logic/reasoning to evaluate alternatives | **Extensive (5)** — minimum **Considerable (4)** |
| Azure Policy at scale | **No** (unless unstated hands-on Policy work) |
| Cloud + security/compliance/PHI/PII | **Yes** |
