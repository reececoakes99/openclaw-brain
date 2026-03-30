# Openclaw Offensive Knowledge Stack — Repo Index
# Total repos: 46
# Last updated: 2026-03-30 11:59 UTC

---

## TIER 1 — CORE OFFENSIVE

### PayloadsAllTheThings
- Path: `openclaw-skills/repos/PayloadsAllTheThings/`
- Source: https://github.com/swisskyrepo/PayloadsAllTheThings
- Domain: Attack payloads, injection strings, exploitation techniques, filter bypasses, web attack methodology
- Trigger: Payload construction, injection testing, bypass techniques, exploitation methodology, web attack technique lookup
- Complements: SecLists for raw wordlists, HackTricks for methodology context

### SecLists
- Path: `openclaw-skills/repos/SecLists/`
- Source: https://github.com/danielmiessler/SecLists
- Domain: Wordlists, fuzzing inputs, credential lists, discovery lists, default credentials, pattern matching
- Trigger: Directory/file brute force, subdomain enumeration, username/password lists, parameter fuzzing, API endpoint discovery, credential stuffing
- Complements: PAT for technique context, Nuclei Templates for automated scanning lists

### HackTricks
- Path: `openclaw-skills/repos/hacktricks/`
- Source: https://github.com/carlospolop/hacktricks
- Domain: Pentest methodology, service enumeration, AD attacks, Kerberos, LDAP, cloud (AWS/GCP/Azure), network protocol exploitation, post-exploitation, lateral movement
- Trigger: Methodology walkthrough, service/port enumeration, AD/cloud attacks, post-exploitation planning, lateral movement
- Complements: PAT for payloads, PEASS-ng for enumeration, GTFOBins for binary abuse

### GTFOBins
- Path: `openclaw-skills/repos/GTFOBins.github.io/_gtfobins/`
- Source: https://github.com/GTFOBins/GTFOBins.github.io
- Domain: Unix binary abuse — SUID exploitation, sudo bypass, shell escapes, file read/write, reverse shells via standard binaries
- Trigger: Living-off-the-land on Linux/Unix, sudo -l analysis, SUID binary exploitation, restricted shell escape
- Complements: HackTricks for broader priv esc methodology, PEASS-ng for automated detection

### PEASS-ng
- Path: `openclaw-skills/repos/PEASS-ng/`
- Source: https://github.com/carlospolop/PEASS-ng
- Domain: Automated privilege escalation enumeration — linPEAS (Linux), winPEAS (Windows)
- Trigger: Post-access enumeration, priv esc vector identification, linPEAS/winPEAS deployment and output interpretation
- Complements: GTFOBins for manual exploitation, HackTricks for methodology behind flagged vectors

---

## TIER 2 — WEB RECON & OSINT

### Nuclei Templates
- Path: `openclaw-skills/repos/nuclei-templates/`
- Source: https://github.com/projectdiscovery/nuclei-templates
- Domain: Automated vulnerability scanning templates — CVE detection, misconfigurations, exposed panels, default credentials, network, DNS, SSL, workflow templates
- Trigger: Running nuclei scans, selecting templates for a specific vulnerability class or CVE, identifying exposed admin panels, detecting misconfigurations at scale
- Primary entry point: `cves/` for CVE-specific templates, `exposures/` for exposed panels and files, `misconfiguration/` for config issues, `network/` for network-layer checks, `default-logins/` for credential checks
- Complements: ExploitDB and PoC-in-GitHub for exploit code behind flagged CVEs, SecLists for credential lists used in default-login templates

### Recon-ng
- Path: `openclaw-skills/repos/recon-ng/`
- Source: https://github.com/lanmaster53/recon-ng
- Domain: Modular web reconnaissance framework — OSINT data gathering, contact harvesting, host enumeration, reporting
- Trigger: Structured OSINT collection, contact and email harvesting via modules, host/domain reconnaissance via framework
- Primary entry point: `modules/` directory organised by category — `recon/`, `discovery/`, `exploitation/`, `import/`, `reporting/`
- Complements: theHarvester for passive email/host harvesting, SpiderFoot for automated OSINT graph building

### theHarvester
- Path: `openclaw-skills/repos/theHarvester/`
- Source: https://github.com/laramies/theHarvester
- Domain: Passive OSINT — email harvesting, subdomain enumeration, host discovery, open port detection via public sources (Google, Bing, Shodan, Hunter, etc.)
- Trigger: Passive email or subdomain gathering, initial target reconnaissance from public sources, identifying exposed hosts without active scanning
- Primary entry point: `theHarvester.py` — review `discovery/` for source modules
- Complements: Subfinder for deeper subdomain enumeration, BBOT for full automated OSINT chain

### SpiderFoot
- Path: `openclaw-skills/repos/spiderfoot/`
- Source: https://github.com/smicallef/spiderfoot
- Domain: Automated OSINT — target profiling across 200+ data sources, IP/domain/email/username/ASN intelligence, threat intelligence correlation
- Trigger: Full automated OSINT profile on a target, threat intel correlation, ASN/IP range mapping, cross-source intelligence aggregation
- Primary entry point: `modules/` for individual data source modules, `sflib.py` for core framework
- Complements: theHarvester for quick passive harvest, Sherlock for username enumeration across platforms

### Sherlock
- Path: `openclaw-skills/repos/sherlock/`
- Source: https://github.com/sherlock-project/sherlock
- Domain: Username enumeration across 400+ social media and online platforms
- Trigger: Any request to enumerate a username across platforms, identify social media presence of a target, OSINT persona mapping
- Primary entry point: `sherlock/sites.md` for platform list, `sherlock/sherlock.py` for execution
- Complements: SpiderFoot for broader OSINT, theHarvester for email correlation

### BBOT
- Path: `openclaw-skills/repos/bbot/`
- Source: https://github.com/blacklanternsecurity/bbot
- Domain: Full-scope automated OSINT and recon — subdomain enumeration, port scanning, web crawling, vulnerability detection, email harvesting, cloud asset discovery, all in one modular pipeline
- Trigger: Full automated recon pipeline on a domain or IP, combining multiple OSINT sources into one run, discovering cloud assets, comprehensive attack surface mapping
- Primary entry point: `bbot/modules/` for individual module reference, README for scan syntax
- Complements: Subfinder and httpx for targeted subdomain/HTTP enumeration, Nuclei Templates for vuln scanning after asset discovery

### Amass
- Path: `openclaw-skills/repos/amass/`
- Source: https://github.com/owasp-amass/amass
- Domain: In-depth attack surface mapping — subdomain enumeration, DNS brute forcing, certificate transparency, ASN and IP range discovery, graph-based relationship mapping
- Trigger: Deep subdomain enumeration, ASN/IP range mapping, certificate transparency lookup, attack surface visualisation
- Primary entry point: `doc/` for usage documentation, `examples/` for config examples
- Complements: Subfinder for fast passive subdomain enum, BBOT for full pipeline integration

### Subfinder
- Path: `openclaw-skills/repos/subfinder/`
- Source: https://github.com/projectdiscovery/subfinder
- Domain: Fast passive subdomain enumeration using multiple passive sources — crt.sh, Shodan, etc.
- Trigger: Quick passive subdomain discovery without brute force, high-speed enumeration for initial footprinting
- Complements: Amass for deep graph mapping, httpx for validating discovered subdomains

### httpx
- Path: `openclaw-skills/repos/httpx/`
- Source: https://github.com/projectdiscovery/httpx
- Domain: Fast multi-purpose HTTP toolkit — validates URLs, extracts title, server, technology, status code, IP, CNAME, CDN info, and hashes at scale
- Trigger: Validating live web services from domain lists, fingerprinting technology stacks, filtering accessible hosts for further auditing
- Complements: Subfinder/BBOT for input, Katana/Gospider for crawling validated hosts

### Katana
- Path: `openclaw-skills/repos/katana/`
- Source: https://github.com/projectdiscovery/katana
- Domain: Next-generation crawler/spider — headless crawling, automated form filling, JS parsing, endpoint discovery, custom headers, proxy support
- Trigger: Deep crawling of a target for endpoints, uncovering hidden parameters/forms, automated link discovery on JS-heavy sites
- Complements: httpx for initial validation, nuclei for scanning discovered endpoints

---

## TIER 3 — EXPLOIT FRAMEWORKS & CVEs

### ExploitDB
- Path: `openclaw-skills/repos/exploitdb/`
- Source: https://github.com/offensive-security/exploitdb
- Domain: Archive of public exploits and shellcode — searchable by CVE, technology, author, and platform
- Trigger: Researching public exploit code for a specific vulnerability or CVE, downloading shellcode, identifying validated PoCs
- Complements: getsploit for command-line search, PoC-in-GitHub for alternative recent PoCs

### Metasploit Framework
- Path: `openclaw-skills/repos/metasploit-framework/`
- Source: https://github.com/rapid7/metasploit-framework
- Domain: World's most used penetration testing framework — thousands of exploit modules, payloads, post-exploitation modules, auxiliary scanners
- Trigger: Weaponised module selection, auxiliary scanning, payload generation, post-exploitation automation
- Primary entry point: `modules/` directory — `exploits/`, `auxiliary/`, `post/`, `payloads/`
- Complements: ExploitDB/CVE for researching which module to use, PEASS-ng for local post-ex intelligence

### getsploit
- Path: `openclaw-skills/repos/getsploit/`
- Source: https://github.com/vulnersCom/getsploit
- Domain: CLI tool for searching exploits in Vulners.com database — searches ExploitDB, Metasploit, Packet Storm, Zero Day Initiative (ZDI), and more
- Trigger: Fast CLI-based exploit research across multiple databases simultaneously
- Complements: ExploitDB for deep manual archive access

### PoC-in-GitHub
- Path: `openclaw-skills/repos/PoC-in-GitHub/`
- Source: https://github.com/nomi-sec/PoC-in-GitHub
- Domain: Curated list of Proof of Concepts (PoC) for CVEs stored on GitHub — organized by CVE year
- Trigger: Finding recent or GitHub-hosted PoC code for a newly discovered CVE, bypassing traditional exploit archives for "bleeding edge" PoCs
- Complements: trickest/cve for vulnerability metadata, ExploitDB for archived exploits

### CVE (trickest/cve)
- Path: `openclaw-skills/repos/cve/`
- Source: https://github.com/trickest/cve
- Domain: Massive CVE metadata database — includes CVSS, descriptions, and linked assets for all historical CVEs
- Trigger: Researching CVE details, severity assessment, identifying affected versions and technology tags
- Complements: PoC-in-GitHub for exploit code matching the CVE, nuclei-templates for scanning templates

### BashBunny Payloads
- Path: `openclaw-skills/repos/bashbunny-payloads/`
- Source: https://github.com/hak5/bashbunny-payloads
- Domain: Physical access payloads for Hak5 Bash Bunny — keystroke injection, network attack payloads, exfiltration, credential harvesting
- Trigger: Any request involving physical access layer attacks, HID injection, hardware-based data exfiltration
- Complements: SecLists for credential/payload lists adapted for physical delivery

---

## TIER 4 — HYBRID CRAWLER/SCRAPER STACK

### Photon
- Path: `openclaw-skills/repos/Photon/`
- Source: https://github.com/s0md3v/Photon
- Domain: OSINT-focused crawler — extracts URLs, emails, social media, files, JS endpoints, secrets, subdomains
- Trigger: Fast OSINT crawl of a target domain to extract links/secrets/contacts in one pass
- Complements: LinkFinder/SecretFinder for JS analysis, gau/waybackurls for passive URL expansion

### GoSpider
- Path: `openclaw-skills/repos/gospider/`
- Source: https://github.com/jaeles-project/gospider
- Domain: Fast Go spider — active crawling with JS parsing, sitemap/robots.txt, 3rd party integration (Archive.org, VT, AlienVault)
- Trigger: Active crawl of live target for endpoint discovery, JS link extraction, multi-target crawling
- Complements: Katana for headless JS crawling, gau/waybackurls for archive data

### Hakrawler
- Path: `openclaw-skills/repos/hakrawler/`
- Source: https://github.com/hakluke/hakrawler
- Domain: Fast Go endpoint crawler — discovers links, forms, JS files, subdomains from HTML/JS
- Trigger: Quick parallel endpoint/asset discovery, fast recon on multiple targets
- Complements: GoSpider for 3rd party source integration, anew for output cleanup

### Crawl4AI
- Path: `openclaw-skills/repos/crawl4ai/`
- Source: https://github.com/unclecode/crawl4ai
- Domain: LLM-native async web crawler — structured data extraction, markdown output, table extraction, JS rendering, stealth headless browser
- Trigger: Extracting structured data from JS-heavy sites, feeding content directly into LLM analysis pipelines
- Complements: Feeds directly into Atomicbot LLM analysis pipeline for structured extraction

### Scrapling
- Path: `openclaw-skills/repos/Scrapling/`
- Source: https://github.com/D4Vinci/Scrapling
- Domain: Adaptive scraping framework — concurrent crawling, multi-session (HTTP + headless), checkpoint-based pause/resume
- Trigger: Full-scale scraping campaigns requiring concurrency control and stealth browser routing
- Complements: Crawl4AI for structured extraction

### Waybackurls
- Path: `openclaw-skills/repos/waybackurls/`
- Source: https://github.com/tomnomnom/waybackurls
- Domain: Passive URL discovery — fetches historical URLs indexed by Wayback Machine for a domain
- Trigger: Passive collection of historical/deprecated endpoints and parameters
- Complements: gau for multi-source aggregation, ParamSpider for archive parameter discovery

### GAU (GetAllUrls)
- Path: `openclaw-skills/repos/gau/`
- Source: https://github.com/lc/gau
- Domain: Multi-source passive URL aggregation — fetches from OTX, Wayback, Common Crawl, and URLScan simultaneously
- Trigger: Maximum passive URL collection from multiple sources
- Complements: waywayback/waybackurls for deep Wayback pulls, anew for deduplication

### ParamSpider
- Path: `openclaw-skills/repos/ParamSpider/`
- Source: https://github.com/devanshbatham/ParamSpider
- Domain: Parameter mining from archives — extracts parameters from Wayback Machine without touching the live target
- Trigger: Passive parameter discovery for hidden/old query params
- Complements: Arjun/x8 for active parameter discovery, PAT for payloads against parameters

### Waymore
- Path: `openclaw-skills/repos/waymore/`
- Source: https://github.com/xnl-h4ck3r/waymore
- Domain: Extended archive/scaper — URLs and responses from Wayback, Common Crawl, OTX, URLScan; includes response downloading
- Trigger: Deep archive crawl with content analysis from historical snapshots
- Complements: SecretFinder for secret extraction from downloaded responses

### LinkFinder
- Path: `openclaw-skills/repos/LinkFinder/`
- Source: https://github.com/GerbenJavado/LinkFinder
- Domain: JS endpoint extractor — regex parsing for hidden endpoints, API paths, parameters, tokens
- Trigger: Extracting API routes and hidden endpoints from JS files
- Complements: SecretFinder for parsing the same files for secrets

### SecretFinder
- Path: `openclaw-skills/repos/SecretFinder/`
- Source: https://github.com/m4ll0k/SecretFinder
- Domain: Secret/token extractor from JS — finds API keys, tokens, credentials, and Cloud keys in client-side code
- Trigger: Scanning JS files for hardcoded credentials or API key exposure
- Complements: LinkFinder for endpoint discovery, Trufflehog/Gitleaks for source code scanning

### GF (Grep Patterns)
- Path: `openclaw-skills/repos/gf/`
- Source: https://github.com/tomnomnom/gf
- Domain: Pattern-based URL filtering — applies grep patterns to triage URLs for vuln classes (XSS, SQLi, SSRF, RCE, etc.)
- Trigger: Filtering large URL lists for testable parameters based on vulnerability patterns
- Complements: gau/waybackurls for input lists, PAT for payloads

### Anew
- Path: `openclaw-skills/repos/anew/`
- Source: https://github.com/tomnomnom/anew
- Domain: Append-only deduplication — appends unique lines, suppressing duplicates across tool outputs
- Trigger: Deduplicating and merging output from multiple discovery tools
- Complements: Used as the universal sink for all multi-tool pipelines

### Arjun / x8
- Paths: `openclaw-skills/repos/Arjun/`, `openclaw-skills/repos/x8/`
- Source: https://github.com/s0md3v/Arjun, https://github.com/Sh1Yo/x8
- Domain: Active parameter discovery — testing for hidden parameters via wordlists or response diffing
- Trigger: Discovering hidden parameters on live endpoints with active testing
- Complements: ParamSpider for passive wordlist construction, PAT for payloads

### Feroxbuster / Gobuster / FFUF
- Paths: `openclaw-skills/repos/feroxbuster/`, `openclaw-skills/repos/gobuster/`, `openclaw-skills/repos/ffuf/`
- Source: https://github.com/epi052/feroxbuster, https://github.com/OJ/gobuster, https://github.com/ffuf/ffuf
- Domain: Path brute-forcing and fuzzing — recursive discovery, directory/vhost busting, multi-position fuzzing
- Trigger: Brute-forcing hidden paths, fuzzing parameters/headers, finding admin panels
- Complements: SecLists for wordlists, anew for results merging

### Gowitness / Aquatone
- Paths: `openclaw-skills/repos/gowitness/`, `openclaw-skills/repos/aquatone/`
- Source: https://github.com/sensepost/gowitness, https://github.com/michenriksen/aquatone
- Domain: Web screenshot utilities — automated visual recon of hosts and subdomains
- Trigger: Visual triage of large asset lists, identifying live services visually
- Complements: Subfinder/httpx for input discovery

### Trufflehog / Gitleaks
- Paths: `openclaw-skills/repos/trufflehog/`, `openclaw-skills/repos/gitleaks/`
- Source: https://github.com/trufflesecurity/trufflehog, https://github.com/gitleaks/gitleaks
- Domain: Secret scanning — detecting credentials and keys in git history, filesystems, and S3 buckets
- Trigger: Scanning repositories or filesystems for exposed secrets and credential leakage
- Complements: SecretFinder for JS runtime secret extraction, HackTricks for post-auth methodology
