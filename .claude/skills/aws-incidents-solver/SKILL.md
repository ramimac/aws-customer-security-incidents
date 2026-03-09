---
name: aws-incidents-solver
description: Solve open GitHub issues in the aws-customer-security-incidents repository. Use this skill when the user asks to address, solve, fix, or work on an issue number, or when they mention adding incidents, threat actors, or security research to this catalog. Triggers on phrases like "address issue #X", "solve issue", "add this incident", or "work on the backlog".
---

# AWS Customer Security Incidents Issue Solver

This skill guides the process of resolving GitHub issues in the ramimac/aws-customer-security-incidents repository by researching security incidents and adding them to the appropriate catalog files.

## Repository Context

This is a documentation repository cataloging publicly disclosed AWS customer security incidents. It contains markdown tables tracking:
- **README.md**: Main incident catalog (customer incidents + vendor-reported case studies)
- **ACTORS.md**: Threat actors and their tools/techniques
- **KEYLEAKS.md**: Research identifying bulk AWS credential leaks
- **SSRF.md**: SSRF exploits targeting AWS environments
- **DISCLOSURE.md**: Responsible disclosure incidents
- **REPORTS.md**: Industry "state of the cloud" security report takeaways

## Issue Resolution Workflow

### Step 1: Fetch the Issue

```bash
gh issue view <NUMBER> --repo ramimac/aws-customer-security-incidents
```

The issue contains:
- **Title**: Short name describing the incident/actor/research
- **Body**: One or more source URLs to research

### Step 2: Research the Sources

1. **Fetch the primary source** from the issue body using WebFetch to extract:
   - Date of incident
   - Root cause / attack vector
   - Escalation or persistence vectors
   - Impact (data stolen, services abused, etc.)
   - Threat actor name (if known)
   - AWS services involved

2. **Search for additional sources** using WebSearch to find better citations

3. **Verify AWS involvement** (see AWS Verification below)

4. **Cross-reference details** across sources - flag conflicts (see Source Conflict Detection below)

5. **Select the best citation** using the source hierarchy below

## AWS Verification

This repository specifically catalogs AWS customer incidents. Before adding an entry, confirm AWS involvement.

### Explicit AWS Evidence (clear to proceed)
- Direct mention of "AWS", "Amazon Web Services"
- AWS account compromise mentioned
- AWS console or CLI access referenced

### Implicit AWS Evidence (acceptable)
Look for AWS-specific services or terminology:

| Category | AWS Services/Terms |
|----------|-------------------|
| Compute | EC2, Lambda, ECS, EKS, Fargate, Lightsail |
| Storage | S3, EBS, EFS, Glacier |
| Database | RDS, DynamoDB, Redshift, DocumentDB, Aurora |
| Identity | IAM, Cognito, STS, SSO, Identity Center |
| Secrets | Secrets Manager, KMS, Parameter Store |
| Network | VPC, CloudFront, Route 53, API Gateway |
| Mail | SES, SNS |
| Container | ECR |
| Metadata | IMDS, 169.254.169.254 |

Also acceptable: References to "cloud credentials" with context suggesting AWS (e.g., company known to use AWS, ~/.aws/ paths, AKIA* access key patterns)

### No AWS Evidence Found

If sources don't confirm AWS involvement:

1. **Add the `pending-details` label:**
```bash
gh issue edit <NUMBER> --repo ramimac/aws-customer-security-incidents --add-label "pending-details"
```

2. **Comment asking for clarification:**
```bash
gh issue comment <NUMBER> --repo ramimac/aws-customer-security-incidents --body "Unable to confirm AWS involvement from the provided sources. The sources mention [what they do mention - e.g., 'cloud infrastructure' or 'Azure']. Can you provide additional context or sources confirming this incident involved AWS?"
```

3. **Do not add the entry** - stop here and inform the user

### Multi-Cloud Incidents
Some incidents span multiple cloud providers. If AWS is one of several affected:
- Still add the entry if AWS-specific details exist
- Note the multi-cloud nature in the entry if relevant

## Source Conflict Detection

Do not parrot unverified claims. Cross-reference key details across sources and flag discrepancies.

### Details to Verify Across Sources
- **Date of incident** - Sources may report discovery date vs. actual breach date
- **Root cause** - Early reports often speculate; later sources may have accurate details
- **Impact numbers** - Threat actor claims vs. company statements often differ significantly
- **Threat actor attribution** - May be disputed or unconfirmed

### When Sources Conflict

**Minor discrepancies** (proceed with caution):
- Slightly different dates (same month) → Use the most authoritative source's date
- Different impact estimates → Use company's official statement if available, or note "claimed" for threat actor statements

**Major conflicts** (flag for manual review):
If sources materially disagree on root cause, AWS involvement, or impact:

1. **Comment on the issue with findings:**
```bash
gh issue comment <NUMBER> --repo ramimac/aws-customer-security-incidents --body "Found conflicting information across sources:

**[Detail in conflict]:**
- Source A ([url]): [claim]
- Source B ([url]): [claim]

Flagging for manual review before adding entry."
```

2. **Add the `pending-details` label**

3. **Do not add the entry** - inform the user of the conflict

### Threat Actor Claims vs. Verified Facts

Be especially skeptical of:
- Data volume claims from threat actors (often inflated)
- Root cause claims from threat actors (may be fabricated)
- "Exclusive" details from news outlets citing anonymous sources

Prefer:
- Official company statements
- Technical analysis from security researchers who examined evidence
- Court documents, regulatory filings, breach notifications

When only threat actor claims exist, use language like:
- "Threat actor claims..." in impact column
- "Alleged [root cause]" if unverified
- Add note: details unverified by victim or researchers

## Source Selection Hierarchy

Always cite the most authoritative source available. When multiple sources exist, prefer higher tiers. Compare publish dates - earlier publication often indicates the original source.

### Tier 1: Original Victim Reports (ALWAYS PREFER)
The victim's own disclosure is the gold standard. Look for:
- **Company security blogs**: `company.com/blog/security-incident`
- **Official security bulletins**: `/security-bulletins/`, `/security-response/`
- **Newsroom security updates**: `/newsroom/security-update`
- **Breach notification letters**: State AG offices (e.g., `dojmt.gov`, `oag.ca.gov`)

Examples from repo: Cloudflare's incident blog, Uber's newsroom, HPE Aruba's security bulletin, TinaCloud's disclosure, Kiln's post-incident report

### Tier 2: Security Research Organizations
Primary research with technical depth. These orgs investigate and publish original analysis:

| Organization | Domain | Specialty |
|--------------|--------|-----------|
| Wiz | wiz.io/blog | Cloud security research |
| Unit42 / Palo Alto | unit42.paloaltonetworks.com | Threat intelligence |
| Sysdig | sysdig.com/blog | Container/cloud threats |
| CrowdStrike | crowdstrike.com/blog | Threat actors, IR |
| Mandiant / Google Cloud | mandiant.com, services.google.com | APT research, M-Trends |
| Datadog Security Labs | securitylabs.datadoghq.com | Cloud attack analysis |
| SentinelOne | sentinelone.com/labs | Malware, threat actors |
| Permiso | permiso.io/blog | Cloud identity attacks |
| Expel | expel.com/blog | IR case studies |
| Cado Security | cadosecurity.com | Cloud forensics |
| AWS Security Blog | aws.amazon.com/blogs/security | AWS-specific guidance |
| CISA | cisa.gov | Advisories, joint alerts |

Also valuable: Aqua Security, Lacework, Rapid7, Kroll, academic papers (DEFCON, Usenix, NDSS)

### Tier 3: News Coverage (LEAST PREFERRED)
News outlets report on incidents but rarely add technical depth. Only use when Tier 1/2 unavailable:
- BleepingComputer, The Record, The Register, TechCrunch, Wired, Ars Technica, CyberNews

**If the issue links to news coverage, always search for a better source.** The news article often cites or links to the original - find it.

### Source Selection Decision Tree

```
1. Does victim have an official disclosure?
   YES → Use it (Tier 1)
   NO  → Continue

2. Did a security research org publish analysis?
   YES → Use the most detailed one (Tier 2)
   NO  → Continue

3. Is news coverage the only option?
   YES → Use it, but note uncertainty in root cause if details are vague
```

### Comparing Multiple Sources

When you find multiple sources:
- **Check publish dates**: Earlier often = original source
- **Compare technical depth**: Prefer sources with CVEs, specific AWS services, IOCs
- **Look for citations**: News articles often cite the real source - follow the chain
- **Prefer archived URLs**: Use web.archive.org or archive.ph for link longevity

### Step 3: Determine Target File(s)

Based on the issue title, labels, and content:

| Indicator | Target File |
|-----------|-------------|
| General breach/incident | README.md (main table) |
| Vendor case study (no company name) | README.md (vendor-reported table) |
| Threat actor/group | ACTORS.md |
| "KEYLEAKS" in title, bulk credential research | KEYLEAKS.md |
| SSRF-related | SSRF.md |
| Responsible disclosure, bug bounty | DISCLOSURE.md |
| Industry report takeaways | REPORTS.md |

Often an incident involves both a new entry AND a new threat actor - add to multiple files when appropriate.

### Step 4: Add Entries

#### README.md Incidents Table
```
| Name | Date | Root Cause | Escalation Vector(s) | Impact | Link to details |
```
- **Date format**: `YYYY, Month` (e.g., `2026, February`)
- **Root cause**: Be specific (e.g., "Unpatched React2Shell vulnerability (CVE-2025-55182)")
- **Escalation**: How attacker pivoted (e.g., "AWS Secrets Manager, Redshift accessed")
- **Impact**: What was compromised (e.g., "2GB data including ~400K user profiles")
- **Links**: Prefer archived URLs; use most authoritative/detailed source
- **Position**: Add chronologically by date

#### ACTORS.md Threat Actors Table
```
| Name | Vectors | Reports |
```
- **Name**: Threat actor/group name
- **Vectors**: Attack methods (e.g., "Exploit unpatched vulnerabilities, data exfiltration")
- **Reports**: Links to threat intelligence reports
- **Position**: Add alphabetically by name

#### KEYLEAKS.md Research Table
```
| Date | Leak | Reference |
```

#### Other files follow similar patterns - read the existing entries for format.

### Step 5: Commit

Format: `Fixes #<issue>: <short description>`

```bash
git add <files>
git commit -m "$(cat <<'EOF'
Fixes #<NUMBER>: <Short Description>

Co-Authored-By: Claude <assistant>
EOF
)"
```

- Single-line subject when possible
- `Fixes #` auto-closes the issue when merged
- Include all changed files in one commit

## Research Tips

- **Always search for better sources** - if the issue links to news, search for victim disclosure or research org analysis
- If the primary source returns 403/blocked, search for the same story on other outlets
- Check if threat actors mentioned are already in ACTORS.md before adding
- For new threat actors, search for additional context on their TTPs and other attacks
- Government/enterprise breaches often have multiple news sources - cross-reference for accuracy
- Look for CVE numbers, specific AWS services, and quantified impact data
- When citing research orgs, prefer the org that discovered/reported the incident first

## Example

**Issue #288**: "LexisNexis" with BleepingComputer URL (news - Tier 3)

**Source research**:
1. BleepingComputer article returned 403
2. Searched for additional sources, found:
   - The Register (news, but more technical detail)
   - The Record (news)
   - CyberPress (news)
3. No victim disclosure found (LexisNexis had no public blog post)
4. No Tier 2 research org coverage yet
5. **Selected**: The Register - most technical depth among available news sources

**AWS Verification**: ✅ CONFIRMED
- Explicit: "AWS infrastructure" mentioned in The Register
- Implicit: Redshift tables, VPC databases, AWS Secrets Manager all referenced
- Multiple sources consistent on AWS involvement

**Source Conflict Check**:
- Date: Consistent (February 2026 across sources)
- Root cause: Consistent (CVE-2025-55182, React2Shell)
- Impact: **Minor conflict** - Threat actor claims 2GB, company says "limited servers with legacy data"
  - Resolution: Used "2GB data" as factual size, noted user count from threat actor claim with "~"

**Research found**:
- Date: February 2026
- Root cause: CVE-2025-55182 (React2Shell) - unpatched React container
- Escalation: AWS Secrets Manager (53 secrets), 536 Redshift tables, 430+ VPC database tables
- Impact: 2GB data, ~400K user profiles including .gov accounts
- Threat actor: FulcrumSec (new, not in ACTORS.md)

**Result**: Added entry to README.md AND FulcrumSec to ACTORS.md, single commit.

---

## Example: Insufficient AWS Evidence

**Issue #XXX**: "Acme Corp Breach" with TechCrunch URL

**Source research**:
1. TechCrunch mentions "cloud infrastructure" but no specific provider
2. Searched for additional sources - no AWS confirmation
3. Company statement says "third-party cloud services" - ambiguous

**AWS Verification**: ❌ NOT CONFIRMED
- No explicit AWS mention
- No implicit AWS services referenced
- Could be Azure, GCP, or other provider

**Action taken**:
```bash
gh issue edit XXX --add-label "pending-details"
gh issue comment XXX --body "Unable to confirm AWS involvement..."
```

**Result**: Entry NOT added. User informed to provide AWS-confirming sources.

---

## Lessons Learned

### Chronological Ordering

**Entries must be inserted in chronological order, not appended to the end of tables.**

- README.md incidents: Order by date (oldest first)
- DISCLOSURE.md: Order by date (oldest first)
- ACTORS.md: Order alphabetically by threat actor name
- REPORTS.md: Order chronologically by report date

When adding an entry, find the correct position based on the date/name and insert there. Do not simply append to the last row.

### Twitter/X Sources

Twitter/X URLs are often inaccessible. When an issue links to `x.com` or `twitter.com`:

1. Try nitter mirrors: `https://nitter.net/username/status/ID`
2. Try archive.org: `https://web.archive.org/web/https://x.com/...`
3. Search for the researcher's name + topic to find blog posts or other coverage
4. If still inaccessible, add `pending-details` label and ask for alternative sources

### One Commit Per Issue

**Always create a separate commit for each issue**, even when processing multiple issues in a batch.

- GitHub reliably auto-closes issues when `Fixes #<NUMBER>` appears in a single-issue commit
- Batch commits with `Fixes #1, #2, #3` often fail to close all referenced issues
- Separate commits also make it easier to revert individual changes if needed

```bash
# Correct: One commit per issue
git add README.md ACTORS.md
git commit -m "Fixes #281: Sysdig AI-assisted intrusion case"

git add ACTORS.md
git commit -m "Fixes #282: TeamPCP threat actor"
```

### Updating Existing Entries

When new research expands on an existing threat actor:

- Check ACTORS.md first to see if the actor already exists
- Update the existing row with new TTPs and additional report links rather than creating a duplicate
- Example: TraderTraitor already existed; added new Ctrl-Alt-Intel report link and expanded vectors
