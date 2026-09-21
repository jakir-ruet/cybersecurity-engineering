## What Netcraft Labs Usually Teach

Netcraft labs focus on:

- Website reconnaissance (who hosts a site, tech stack)
- Identifying hosting providers and infrastructure
- Detecting phishing or suspicious domains
- Passive information gathering (no direct attacks)

| Task | Activity                   | What You Do                                   | Purpose                                          |
| ---- | -------------------------- | --------------------------------------------- | ------------------------------------------------ |
| 1    | Site Report Analysis       | Look up a domain in Netcraft Site Report      | Identify hosting provider, server, OS            |
| 2    | Subdomain Enumeration      | Find subdomains linked to the main domain     | Discover additional assets / attack surface      |
| 3    | SSL/TLS Inspection         | Examine certificate details                   | Verify issuer, validity, and associated domains  |
| 4    | Hosting History Review     | Check historical hosting data                 | See changes in infrastructure over time          |
| 5    | IP & Network Info          | Analyze IP address and ownership              | Understand where the site is hosted              |
| 6    | Technology Stack Detection | Identify server software and frameworks       | Learn what technologies power the site           |
| 7    | Domain Information (WHOIS) | Check domain registration details             | Find owner, registrar, and registration dates    |
| 8    | Phishing Detection         | Assess if a site is suspicious                | Identify malicious or fake websites              |
| 9    | CDN / Proxy Detection      | Determine if site uses CDN (e.g., Cloudflare) | Understand traffic routing and protection layers |
| 10   | Risk & Reputation Analysis | Review trust and risk indicators              | Evaluate security posture of the site            |

### Find these

**Target domain is 🌐 sunitlimited.com**

| Step | Command                           | Purpose                       | What You Should Look For                             |
| ---- | --------------------------------- | ----------------------------- | ---------------------------------------------------- |
| 1    | `nslookup sunitlimited.com`       | DNS resolution (find IP)      | IP address, DNS server info                          |
| 2    | `dig sunitlimited.com +short`     | Quick IP lookup               | Single-line IP result                                |
| 3    | `whatweb http://sunitlimited.com` | Web technology fingerprinting | Web server, CMS, frameworks, email leaks             |
| 4    | `nmap -sV sunitlimited.com`       | Service & port scanning       | Open ports, service versions (FTP, HTTP, SMTP, etc.) |

**Final Lab Results (sunitlimited.com)**

| Item             | Result                                                            | Remarks                                            |
| ---------------- | ----------------------------------------------------------------- | -------------------------------------------------- |
| IP address       | **162.0.215.134**                                                 | Shared hosting IP (web-hosting.com infrastructure) |
| Hosting provider | **Web Hosting/server375-3.web-hosting.com**                       | Shared hosting environment                         |
| Web server       | **LiteSpeed + HAProxy (reverse proxy)**                           | High-performance web stack with proxy layer        |
| SSL issuer       | **Not explicitly shown (likely Let’s Encrypt via hosting stack)** | Needs SSL scan to confirm                          |
| First seen date  | **Not provided in your output**                                   | Would come from Netcraft report                    |
| Risk rating      | **Low–Medium**                                                    | Shared hosting + many exposed services             |
