# Openclaw Repo Index

## PayloadsAllTheThings
- Path: `openclaw-skills/repos/PayloadsAllTheThings/`
- Source: https://github.com/swisskyrepo/PayloadsAllTheThings
- Domain: Offensive payloads, exploitation techniques, injection strings, bypasses, web attacks, methodology
- Trigger: Payload construction, injection testing, bypass techniques, exploitation methodology, web attack technique lookup
- Complements: SecLists for raw wordlists to pair with identified attack class

## SecLists
- Path: `openclaw-skills/repos/SecLists/`
- Source: https://github.com/danielmiessler/SecLists
- Domain: Wordlists, fuzzing lists, enumeration lists, credential lists, discovery lists, default credentials, pattern matching
- Trigger: Directory brute force, subdomain enumeration, username/password lists, parameter fuzzing, API endpoint discovery, credential stuffing
- Complements: PayloadsAllTheThings for technique context behind the list being used

## HackTricks
- Path: `openclaw-skills/repos/hacktricks/`
- Source: https://github.com/carlospolop/hacktricks
- Domain: Comprehensive pentest methodology, service enumeration, privilege escalation, Active Directory attacks, cloud attacks, network protocol exploitation, CTF techniques, post-exploitation
- Trigger: Any request for methodology, how-to enumeration of a specific service or port, AD/Kerberos/LDAP attacks, cloud pentesting (AWS/GCP/Azure), pentesting a specific technology stack, post-exploitation techniques, lateral movement
- Complements: PAT for payloads, PEASS-ng for automated enumeration execution, GTFOBins for binary abuse after gaining access
- Primary entry point: Navigate by topic — `pentesting-web/`, `windows-hardening/`, `linux-hardening/`, `network-services-pentesting/`, `cloud-security/`, `generic-methodologies/`

## GTFOBins
- Path: `openclaw-skills/repos/GTFOBins.github.io/`
- Source: https://github.com/GTFOBins/GTFOBins.github.io
- Domain: Unix binary abuse — privilege escalation, sudo bypass, SUID exploitation, shell escape, file read/write, reverse shells via standard binaries
- Trigger: Any request involving living-off-the-land on Linux/Unix, abusing a specific binary for priv esc, sudo -l output analysis, SUID binary exploitation, escaping restricted shells, gaining shells via unexpected binaries
- Complements: HackTricks for broader priv esc methodology, PEASS-ng for automated detection of exploitable binaries
- Primary entry point: `_gtfobins/` directory — one `.md` file per binary (e.g. `_gtfobins/vim.md`, `_gtfobins/python.md`)

## PEASS-ng
- Path: `openclaw-skills/repos/PEASS-ng/`
- Source: https://github.com/carlospolop/PEASS-ng
- Domain: Automated privilege escalation enumeration scripts for Linux (linPEAS) and Windows (winPEAS)
- Trigger: Any request to run local enumeration post-access, identify priv esc vectors automatically, understand linPEAS/winPEAS output, deploy enumeration scripts to a compromised host
- Complements: GTFOBins for manual exploitation of findings, HackTricks for methodology behind flagged vectors
- Primary entry point: `linPEAS/` for Linux enumeration, `winPEAS/` for Windows enumeration
