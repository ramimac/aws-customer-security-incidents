### Catalog of AWS Exploits via SSRF

[Server-side request forgery](https://owasp.org/Top10/A10_2021-Server-Side_Request_Forgery_%28SSRF%29/) is a class of attack that is not cloud or AWS specific. However, the existence of cloud metadata services, such as [IMDS](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ec2-instance-metadata.html) in AWS, have historically allowed for a substantial straightforward impact when SSRF is achieved on a cloud hosted application. For that reason, we include this list of SSRF attacks against AWS environments.

* October 2014 - [Prezi Got Pwned: A Tale of Responsible Disclosure](https://engineering.prezi.com/prezi-got-pwned-a-tale-of-responsible-disclosure-ccdc71bb6dd1)
* [Bypassing SSRF Protection to Exfiltrate AWS Metadata from LarkSuite](https://sirleeroyjenkins.medium.com/bypassing-ssrf-protection-to-exfiltrate-aws-metadata-from-larksuite-bf99a3599462)
* [ESEA Server-Side Request Forgery and Querying AWS Meta Data](https://buer.haus/2016/04/18/esea-server-side-request-forgery-and-querying-aws-meta-data/)
* [A pair of Plotly bugs: Stored XSS and AWS Metadata SSRF](https://web.archive.org/web/20170527104436/https://ysx.me.uk/a-pair-of-plotly-bugs-stored-xss-and-aws-metadata-ssrf/)
* [Dropbox - Full Response SSRF via Google Drive](https://github.com/httpvoid/writeups/blob/main/Hacking-Google-Drive-Integrations.md#dropboxs-full-read-ssrf)
* [Mandiant - Old Services, New Tricks: Cloud Metadata Abuse by UNC2903](https://www.mandiant.com/resources/blog/cloud-metadata-abuse-unc2903)
* [SSRF leads to access AWS metadata.](https://infosecwriteups.com/ssrf-leads-to-access-aws-metadata-21952c220aeb)
* [Escalating SSRF to RCE](https://sanderwind.medium.com/escalating-ssrf-to-rce-7c0147371c40)
* [SSRF Leads To AWS Metadata Exposure](https://systemweakness.com/ssrf-leads-to-aws-metadata-exposure-8b4c3424755b)
* [How I discovered an SSRF leading to AWS Metadata Leakage](https://techkranti.com/ssrf-aws-metadata-leakage/)
* [Exploitation of an SSRF vulnerability against EC2 IMDSv2](https://www.yassineaboukir.com/blog/exploitation-of-an-SSRF-vulnerability-against-EC2-IMDSv2/)
* [Mozilla - AWS SSRF to Pull AWS Metadata and Keys](https://bugzilla.mozilla.org/show_bug.cgi?id=1550366)
* [Full read SSRF in www.evernote.com that can leak aws metadata and local file inclusion](https://hackerone.com/reports/1189367) |
* [SSRF allows reading AWS EC2 metadata using "readapi" variable in Streamlabs Cloudbot](https://hackerone.com/reports/1108418)
* [Server Side Request Forgery (SSRF) at app.hellosign.com leads to AWS private keys disclosure](https://hackerone.com/reports/923132)
* [SSRF via Office file thumbnails](https://hackerone.com/reports/671935)
* [Getting AWS creds via SSRF on rss.app](https://ruse.tech/blogs/rss-app-ssrf)
* [AWS takeover through SSRF in JavaScript](https://10degres.net/aws-takeover-through-ssrf-in-javascript/)
* [Yahoo Small Business (Luminate) and the Not-So-Secret Keys](https://dos.sh/blog/2017/6/21/yahoo-small-business-luminate-and-the-not-so-secret-keys)
* [Bug Bounty Story: Escalating SSRF to RCE on AWS](https://hg8.sh/posts/bugbounty/ssrf-to-rce-aws/)
* [A Nifty SSRF Bug Bounty Write Up](https://hack-ed.net/2017/11/07/a-nifty-ssrf-bug-bounty-write-up/)
* [Mozilla Hubs Cloud: cloud api credentials exposure](https://bugzilla.mozilla.org/show_bug.cgi?id=1707898)
* [Lacework Labs: New surge in AWS credential compromises tied to Grafana SSRF attacks](https://www.lacework.com/blog/new-surge-in-aws-credential-compromises-tied-to-grafana-ssrf-attacks/)
* [EC2 User-data to RCE](https://medium.com/@xploiterd/ec2-user-data-to-rce-f601264a75c2)
* [Server Side Request Forgery (SSRF) via Analytics Reports](https://hackerone.com/reports/2262382)
* [SSRF to read AWS metaData at https://█████/ \[HtUS\]](https://hackerone.com/reports/1624140)
* [SSRF on █████████ Allowing internal server data access](https://hackerone.com/reports/326040)
* [The Unusual Case of Status code- 301 Redirection to AWS Security Credentials Compromise](https://logicbomb.medium.com/the-unusual-case-of-open-redirection-to-aws-security-credentials-compromise-59acc312f02b)

For more about this attack, please see [Hacking the Cloud - Steal EC2 Metadata Credentials via SSRF](https://hackingthe.cloud/aws/exploitation/ec2-metadata-ssrf/)
