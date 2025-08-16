## Disclosure (responsible, coordinated, public)

This is a partial directory of incidents impacting individuals, or disclosed attack attempts or chains with no incident.

We have not compiled the periodic reports of cryptomining due to compromised credentials. [1](https://vertis.io/2013/12/16/unauthorised-litecoin-mining/) [2](https://readwrite.com/amazon-web-services-hack-bitcoin-miners-github/) [3](http://www.nvenky.in/2014/03/bitcoin-mining-closed-my-aws-account.html)


| Date | Vulnerability | Reference |
| ------------- | ------------- | ------------- |
| 2014, Dec | Credentials leaked in Github | [My AWS Account Got Compromised](https://xingwu.me/2014/12/10/My-AWS-Account-Got-Compromised/) | 
| 2016, Dec | Credentials leaked in npm package | [Security Incident - AWS S3 Access Key Exposure](https://blog.emberjs.com/security-incident-aws-s3-key-exposure/) | 
| 2019, May | Credentials leaked in exposed GitLab instance | [Samsung spilled SmartThings app source code and secret keys](https://techcrunch.com/2019/05/08/samsung-source-code-leak/) | 
| 2019, May | Credentials leaked in Github | [AWS secret key and NPM token leaked in MEW GitHub repos](https://github.com/Ravirajrao/HackerOne-Reports/blob/master/%23549341%20AWS%20secret%20key%20and%20NPM%20token%20leaked%20in%20MEW%20GitHub%20repos.pdf) | 
| 2020, Feb | Credentials leaked in repository | [Access to Glassdoor's Infra (AWS) and BitBucket account through leaked repo](https://hackerone.com/reports/801531) | 
| 2021, Jan | Analyzed 3,000 documents, found 1 public s3 bucket with PIIes | [The Need to Protect Public AWS SSM Documents](https://research.checkpoint.com/2021/the-need-to-protect-public-aws-ssm-documents-what-the-research-shows/) |
| 2021, Apr | Subdomain takeover, deleted EC2 instance  | [Subdomain takeover of www2.growasyouplan.com](https://hackerone.com/reports/1179193) |
| 2021, Oct | AWS Creds hardcoded in MSI | [Hardcoded AWS credentials in ███████.msi](https://hackerone.com/reports/1368690) |
| 2021, Nov | Potential subdomain takeover, dangling CNAME  | [Possible Domain Takeover on AWS Instance](https://hackerone.com/reports/1390782) |
| 2021, Nov | Subdomain takeover, deleted S3 bucket  | [Subdomain takeover of images.crossinstall.com](https://hackerone.com/reports/1406335) |
| 2021, Dec | Account takeover via Cognito user email change | [Flickr Account Takeover using AWS Cognito API](https://hackerone.com/reports/1342088) |
| 2022, Jan | NoSQL-Injection discloses discloses S3 File Upload URLs | [NoSQL-Injection discloses S3 File Upload URLs](https://hackerone.com/reports/1458020) |
| 2022, May | Malicious update to `ctx` Python library | [Malicious Python library CTX removed from PyPI repo](https://portswigger.net/daily-swig/malicious-python-library-ctx-removed-from-pypi-repo) |
| 2022, Oct | Subdomain takeover, deleted S3 bucket | [Subdomain takeover at http://test.www.midigator.com](https://hackerone.com/reports/1718371) |
| 2022, Nov | AWS credentials in string constant in public python package | [Infosys leaked FullAdminAccess AWS keys on PyPi for over a year](https://tomforb.es/infosys-leaked-fulladminaccess-aws-keys-on-pypi-for-over-a-year/) |
| 2022, Nov | Public RDS snapshots | [Oops, I Leaked It Again](https://www.mitiga.io/blog/how-mitiga-found-pii-in-exposed-amazon-rds-snapshots) |
| 2022, Sep | AWS credentials leaked in code repository | [Shiba Inu cloud credentials leaked on a public repository!](v) |
| 2022, Dec | Lack of forced verification on email update in AWS Cognito | [Account Takeover Due to Cognito Misconfiguration Earns Me €xxxx](https://medium.com/@mukundbhuva/account-takeover-due-to-cognito-misconfiguration-earns-me-xxxx-3a7b8bb9a619) |
| 2023, Jan | AWS credentials found in 57 PyPi packages | [I scanned every package on PyPi and found 57 live AWS keys](https://tomforb.es/i-scanned-every-package-on-pypi-and-found-57-live-aws-keys/) |
| 2023, Jan | AWS credentials disclosed in client-side source | [Owning half of a government assets through AWS](https://crypt0g30rgy.github.io/post/AWSTakeover) |
| 2023, Feb | RCE in Lambda function with access to AWS credentials via /proc/*/environ | [Facebook bug: A Journey from Code Execution to S3 Data Leak](https://medium.com/@win3zz/facebook-bug-a-journey-from-code-execution-to-s3-data-leak-698b7d2b02ef) |
| 2023, Mar | Staging environment file leaked, revealing AWS Access Keys and Secrets | [Saudi social media app leaks user info and pictures](https://cybernews.com/privacy/saudi-social-media-app-leaks-user-info/) |
| 2023, Mar | Passive subdomain takeover | [Passive Takeover - uncovering (and emulating) an expensive subdomain takeover campaign](https://kmsec.uk/blog/passive-takeover/) |
| 2023, Mar | 550 IPs vulnerable to SSRF via Host header, likely due to a vulnerable Lightsail image | [Finding Hundreds of SSRF Vulnerabilities on AWS](https://trickest.com/blog/ssrf-vulnerabilities-on-aws/) |
| 2023, Jun | Credentials in node env file in public S3 bucket | [TripValet.com Leaks Passwords and Stripe Credentials](https://phillips.technology/blog/tripvalet-payment-breach/) |
| 2023, Mar | Staging environment file leaked, revealing AWS Access Keys and Secrets | [Saudi social media app leaks user info and pictures](https://cybernews.com/privacy/saudi-social-media-app-leaks-user-info/) |
| 2023, Aug | librsvg memory leakage exposes Basecamp AWS keys | [AWS keys and user cookie leakage via uninitialized memory leak in outdated librsvg version in Basecamp](https://hackerone.com/reports/2107680) |
| 2024, Feb | Access Key exposed in HTML | [Football Australia leak exposes players’ details](https://cybernews.com/security/football-australia-leak-expose-players/) |
| 2024, Mar | Write permissions to S3 bucket, upload JS that steals credentials | [From S3 bucket to internal network operation](https://medium.com/@red.whisperer/from-s3-bucket-to-internal-network-operation-8073954932b4) |
| 2024, April | AWS credentials leaked on Postman’s Public API Network | [(The) Postman Carries Lots of Secrets](https://trufflesecurity.com/blog/postman-carries-lots-of-secrets) |
| 2024, May | Publicly traded company exposed 8m+ PII records in DocumentDB Snapshot | [Publicly Exposed AWS Document DB Snapshots](https://ramimac.me/exposed-docdb) |
| 2024, June | PHP_INFO disclosed credentials, resulting in SES abuse | [Suspecting that access tokens were leaked: Where to look for leak?](https://www.reddit.com/r/aws/comments/1b3340r/suspecting_that_access_tokens_were_leaked_where/) |
| 2024, July | Kubernetes escape in SAP AI Core allowed access to Loki config, leaking AWS credentials with access to S3 | [SAPwned: SAP AI vulnerabilities expose customers’ cloud environments and private AI artifacts](https://www.wiz.io/blog/sapwned-sap-ai-vulnerabilities-ai-security) |
| 2024, July | Hard-coded AWS credential in JS | [how to pwn a billion dollar vc firm using inspect element](https://kibty.town/blog/a16z/) |
| 2024, December | AWS Access Keys leaked via Java Spring Actuator heapdump | [Customer data from 800,000 electric cars and owners exposed online](https://www.bleepingcomputer.com/news/security/customer-data-from-800-000-electric-cars-and-owners-exposed-online/)
| 2025, February | ~150 S3 buckets with dangling references taking over | [8 Million Requests Later, We Made The SolarWinds Supply Chain Attack Look Amateur](https://labs.watchtowr.com/8-million-requests-later-we-made-the-solarwinds-supply-chain-attack-look-amateur/)
| 2025, February | Hardcoded AWS Access Key in Eight Sleep mattress firmware | [Removing Jeff Bezos From My Bed](https://trufflesecurity.com/blog/removing-jeff-bezos-from-my-bed) | 
| 2025, March | Multiple AWS credentials exposed publicly due to tj-actions | [GitHub Action tj-actions/changed-files supply chain attack](https://www.wiz.io/blog/github-action-tj-actions-changed-files-supply-chain-attack-cve-2025-30066) | 
| 2025, April | AWS Access Keys in frontend JS, resulting in SES abuse | [I Accidentally Exposed AWS Keys. What Happened Next Was a Masterclass in Cloud Persistence](https://medium.com/@bassel.afrem/i-accidentally-exposed-aws-keys-what-happened-next-was-a-masterclass-in-cloud-persistence-8a5154e4d31f) |
| 2025, June | AWS Access Keys leaked in API response, registration of a non-existant logging bucket, cross-tenant compromise | [OneLogin, Many Issues: How I Pivoted from a Trial Tenant to Compromising Customer Signing Keys](https://specterops.io/blog/2025/06/10/onelogin-many-issues-how-i-pivoted-from-a-trial-tenant-to-compromising-customer-signing-keys/) | 
| 2025, July | Compromised AWS Access Key, access to Confluence DB, forge and insert a rogue token for any user | [When too much access is not enough: a story about Confluence and tokens](https://blog.quarkslab.com/a-story-about-confluence-and-tokens.html) |