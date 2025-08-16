## Key Leaks: historic research identifying bulk AWS Secrets 

| Date | Leak | Reference |
| ------------- | ------------- | ------------- |
| 2012, March | Secrets in public AMIs | [A Security Analysis of Amazon’s Elastic Compute Cloud Service](https://seclab.nu/static/publications/sac2012ec2.pdf) |
| 2019, February | 4,648 unique AWS Access Key IDs in Github | [How Bad Can It Git? Characterizing Secret Leakage in Public GitHub Repositories](https://www.ndss-symposium.org/wp-content/uploads/2019/02/ndss2019_04B-3_Meli_paper.pdf) |
| 2019, August | 50 Access Keys in public EBS volumes | [More Keys than a Piano: Finding Secrets in Publicly Exposed EBS Volumes](https://media.defcon.org/DEF%20CON%2027/DEF%20CON%2027%20presentations/DEFCON-27-Ben-Morris-More-Keys-Than-A-Piano-Finding-Secrets-In-Publicly-Exposed-Ebs-Volumes.pdf) |
| 2020, September | ~25,000 AWS Access Keys exposed via Github | [Reliaquest - Access Keys Exposed: More Than 40% Are For Database Stores](https://www.reliaquest.com/blog/access-keys-exposed-more-than-40-are-for-database-stores/) | 
| 2021, January | AWS Access Tokens in Public AMI Images | [Hunting for Sensitive Data in Public Amazon Images (AMI)](https://blog.lethalbit.com/hunting-for-sensitive-data-in-public-amazon-images-ami/) |
| 2021, November | 1,500+ AWS credentials in Docker Hub images | [Scanning Millions of Publicly Exposed Docker Containers – Thousands of Secrets Leaked (Wave 5)](https://redhuntlabs.com/blog/scanning-millions-of-publicly-exposed-docker-containers-thousands-of-secrets-leaked/) |
| 2022, September | 1,859 Android and iOS apps with AWS credentials | [Mobile App Supply Chain Vulnerabilities Could Endanger Sensitive Business Information](https://symantec-enterprise-blogs.security.com/blogs/threat-intelligence/mobile-supply-chain-aws) |
| 2023, July | 1,213 AWS Secrets in Docker images | [Secrets Revealed in Container Images: An Internet-wide Study on Occurrence and Impact](https://arxiv.org/pdf/2307.03958.pdf) |
| 2023, August | Over-privileged cloud credentials in 1,667 mobile applications | [Credit Karma: Understanding Security Implications of Exposed Cloud Services through Automated Capability Inference](https://www.usenix.org/system/files/usenixsecurity23-wang-xueqiang-karma.pdf) |
| 2023, September | 11-12 AWS credentials in `.git` of Alexa Top 1M | [4,500 of the Top 1 Million Websites Leaked Source Code, Secrets](https://trufflesecurity.com/blog/4500-of-the-top-1-million-websites-leaked-source-code-secrets/) |
| 2023, October | over 140 unique active, plaintext credentials to third-party services like OpenAI, AWS, GitHub, and others in Kaggle data | [Analyzing the Security of Machine Learning Research Code](https://developer.nvidia.com/blog/analyzing-the-security-of-machine-learning-research-code/) |
| 2023, November | 2,897 AWS Access Tokens in StackExchange dataset | [I analyzed stackoverflow](https://matan-h.com/analyze-stackoverflow) |
| 2024, April | 3 AWS Credentials leaked in public Gists in a seven day period | [Do Secrets Leak on Public GitHub Gists in 2024?](https://trufflesecurity.com/blog/do-secrets-leak-on-public-github-gists-in-2024) |
| 2024, April | 111 valid AWS keys leaks, 14 belonging to root users in public ECR Registry images | [Securing the Cloud: Detecting and Reporting Sensitive Data in ECR Images](https://badshah.io/talks/slides/2024-04-27-Detecting-And-Reporting-Sensitive-Data-In-ECR.pdf) |
| 2024, May | over 200 valid AWS credentials in Public AMI Images | [AWS CloudQuarry: Digging for Secrets in Public AMIs](https://securitycafe.ro/2024/05/08/aws-cloudquarry-digging-for-secrets-in-public-amis/) |
| 2024, May | Bitbucket secured variables leak AWS keys in plain text through artifact objects | [Holes in Your Bitbucket: Why Your CI/CD Pipeline Is Leaking Secrets](https://cloud.google.com/blog/topics/threat-intelligence/bitbucket-pipeline-leaking-secrets/) |
| 2024, July | Leaked Secrets in Public Jenkins Logs, including 6 AWS keys | [Leaked Secrets in Public Jenkins Logs](https://trufflesecurity.com/blog/leaked-secrets-in-public-jenkins-logs) |
| 2024, August | Leaked secrets via Virustotal's Retrohunt, Passive DNS "more than 78,000 dangling cloud resources linked to 66,000 apex domains" | [Thousands of Corporate Secrets Were Left Exposed. This Guy Found Them All](https://www.wired.com/story/secret-hunting-bill-demirkapi/), [Secrets and Shadows: Leveraging Big Data for Vulnerability Discovery at Scale](https://defcon.org/html/defcon-32/dc-32-speakers.html#54509)
| 2024, August | 1,185 leaked AWS Access Keys in exposed `.env` | [Leaked Environment Variables Allow Large-Scale Extortion Operation of Cloud Environments](https://unit42.paloaltonetworks.com/large-scale-cloud-extortion-operation/)
| 2024, October | Hardcoded AWS Access Keys in mobile apps | [Exposing the Danger Within: Hardcoded Cloud Credentials in Popular Mobile Apps](https://www.security.com/threat-intelligence/exposing-danger-within-hardcoded-cloud-credentials-popular-mobile-apps)
| 2024, October | Numerous leaked credentials scraped from exposed `.git` configurations | [EMERALDWHALE: 15k Cloud Credentials Stolen in Operation Targeting Exposed Git Config Files](https://sysdig.com/blog/emeraldwhale/)
| 2024, December | 1,526 leaked AWS credentials via environment files (.env), configuration files, exposed git repositories (.git), etc. | [From Vulnerabilities to Breaches: The Shiny Nemesis Cyber Operation](https://www.vpnmentor.com/news/shiny-nemesis-report/)
| 2025, January | 4 valid AWS credentials in Firefox Extensions | [Mining All 30,000 Firefox Extensions for Goodies & Baddies](https://harrisonm.com/blog/mining-firefox-extensions)
| 2025, February | Multiple AWS Access Keys in Common Crawl data set | [Research finds 12,000 ‘Live’ API Keys and Passwords in DeepSeek's Training Data](https://trufflesecurity.com/blog/research-finds-12-000-live-api-keys-and-passwords-in-deepseek-s-training-data) | 
| 2025, March | over 7,000 valid AWS credentials exposed on DockerHub | [Fresh From The Docks: Uncovering 100,000 Valid Secrets in DockerHub](https://blog.gitguardian.com/fresh-from-the-docks-uncovering-100-000-valid-secrets-in-dockerhub/) | 
| 2025, July | 130 AWS Access Keys in Dangling "Oops" Commits | [How I Scanned all of GitHub’s “Oops Commits” for Leaked Secrets](https://trufflesecurity.com/blog/guest-post-how-i-scanned-all-of-github-s-oops-commits-for-leaked-secrets) |
| 2025, July | 27 AWS Access Keys in DockerHub images | [Stop the Leak: Scanning Containers for Exposed Secrets](https://www.binarly.io/blog/stop-the-leak-scanning-containers-for-exposed-secrets) |



