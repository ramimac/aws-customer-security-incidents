# Research Notes

This file documents research leads and search terms for finding AWS customer security incidents.

## Non-English Search Terms

These terms were prepared but not executed due to web search budget limits. Use in future research sessions.

### Japanese
**Search terms:**
- `AWS 情報漏洩` (AWS information leak)
- `AWS セキュリティインシデント` (AWS security incident)
- `AWS 不正アクセス` (AWS unauthorized access)
- `AWS 侵害` (AWS breach)
- `クラウド 情報流出 AWS` (cloud data leak AWS)
- `S3 バケット 漏洩` (S3 bucket leak)
- `AWS 認証情報 流出` (AWS credentials leak)

**Sites:**
- security-next.com
- scan.netsecurity.ne.jp
- jpcert.or.jp
- ipa.go.jp

### Korean
**Search terms:**
- `AWS 정보유출` (AWS information leak)
- `AWS 보안사고` (AWS security incident)
- `AWS 침해` (AWS breach)
- `AWS 해킹` (AWS hacking)
- `클라우드 보안 AWS 사고` (cloud security AWS incident)
- `S3 버킷 유출` (S3 bucket leak)
- `AWS 자격증명 유출` (AWS credential leak)

**Sites:**
- boannews.com
- dailysecu.com
- kisa.or.kr
- zdnet.co.kr

### German
**Search terms:**
- `AWS Datenleck` (AWS data leak)
- `AWS Sicherheitsvorfall` (AWS security incident)
- `AWS Datenpanne` (AWS data breach)
- `AWS Hackerangriff` (AWS hacker attack)
- `Cloud Sicherheit AWS Vorfall` (cloud security AWS incident)
- `S3 Bucket Leak Deutschland` (S3 bucket leak Germany)
- `AWS Zugangsdaten gestohlen` (AWS credentials stolen)

**Sites:**
- heise.de
- golem.de
- bsi.bund.de
- datenschutz.de

### French
**Search terms:**
- `AWS fuite de données` (AWS data leak)
- `AWS incident de sécurité` (AWS security incident)
- `AWS violation de données` (AWS data breach)
- `AWS piratage` (AWS hacking)
- `Cloud sécurité AWS incident` (cloud security AWS incident)
- `S3 bucket fuite France` (S3 bucket leak France)
- `AWS identifiants volés` (AWS credentials stolen)

**Sites:**
- cnil.fr
- cert.ssi.gouv.fr
- lemondeinformatique.fr
- 01net.com

### Portuguese (Brazil)
**Search terms:**
- `AWS vazamento de dados` (AWS data leak)
- `AWS incidente de segurança` (AWS security incident)
- `AWS violação` (AWS breach)
- `AWS invasão` (AWS intrusion)
- `Nuvem segurança AWS incidente`
- `AWS credenciais vazadas` (AWS credentials leaked)

**Sites:**
- canaltech.com.br
- techtudo.com.br
- cert.br

### Spanish (LATAM)
**Search terms:**
- `AWS fuga de datos` (AWS data leak)
- `AWS incidente de seguridad` (AWS security incident)
- `AWS brecha de datos` (AWS data breach)
- `AWS hackeo` (AWS hacking)
- `Nube seguridad AWS incidente`
- `AWS credenciales robadas` (AWS credentials stolen)

**Sites:**
- welivesecurity.com/la-es
- argentina.gob.ar/ciberseguridad

### Chinese (Simplified & Traditional)
**Search terms:**
- `AWS 数据泄露` (AWS data leak)
- `AWS 安全事件` (AWS security incident)
- `AWS 入侵` (AWS intrusion)
- `AWS 黑客攻击` (AWS hacker attack)
- `云安全 AWS 事故` (cloud security AWS incident)
- `S3 存储桶泄露` (S3 bucket leak)
- `AWS 凭证泄露` (AWS credential leak)

**Sites:**
- freebuf.com
- secrss.com
- anquanke.com
- ithome.com.tw (Taiwan)

## Data Protection Authorities

### High-Value (detailed technical decisions)
| Authority | Domain | Search Strategy |
|-----------|--------|-----------------|
| Singapore PDPC | pdpc.gov.sg | `site:pdpc.gov.sg decision AWS S3 "access key"` |
| US FTC | ftc.gov | `site:ftc.gov complaint AWS credentials breach` |
| US State AGs | oag.ca.gov, atg.wa.gov, dojmt.gov | Searchable breach notification databases |
| Canada OPC | priv.gc.ca | `site:priv.gc.ca pipeda findings cloud server` |

### Medium-Value
| Authority | Domain | Notes |
|-----------|--------|-------|
| UK ICO | ico.org.uk | Large fines, sometimes lacks cloud specifics |
| Hong Kong PCPD | pcpd.org.hk | Detailed reports but ransomware-focused |
| US HHS OCR | hhs.gov/ocr | HIPAA breaches - manual review needed |

### Low-Value (limited technical detail)
- Ireland DPC (GDPR focus, not cloud infrastructure)
- Australia OAIC (aggregate statistics)
- France CNIL (consent/cookies focus)
- Germany/Netherlands/Spain (language barriers, fragmented)

## Security Research Organizations

### Tier 1 (publish case studies with AWS details)
- Wiz (wiz.io/blog)
- Sysdig (sysdig.com/blog)
- Datadog Security Labs (securitylabs.datadoghq.com)
- Permiso (permiso.io/blog)
- Unit42 (unit42.paloaltonetworks.com)

### Tier 2 (anonymized or technique-focused)
- CrowdStrike (threat trends)
- SentinelOne (malware analysis)
- Aqua Security (threat research)
- Cado Security (anonymized forensics)
- Lacework (detection methodology)

## Leads to Investigate

### Unverified AWS involvement
- MGM Resorts (Canada OPC) - "cloud server" mentioned, AWS unconfirmed
- Kroll insurance case (Jan 2026) - "cloud-based" but AWS unverified
- Eatigo (Singapore PDPC) - cloud provider not specified

### Threat actors for ACTORS.md
- Codefinger - S3 SSE-C ransomware group (Jan 2025)
