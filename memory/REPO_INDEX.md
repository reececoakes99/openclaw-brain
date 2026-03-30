# Openclaw Repo Index

## PayloadsAllTheThings
- Path: `openclaw-skills/repos/PayloadsAllTheThings/`
- Source: https://github.com/swisskyrepo/PayloadsAllTheThings
- Domain: Offensive security — payloads, exploitation techniques, injections, bypasses, privilege escalation, web attacks, network attacks, methodology
- Trigger conditions: Any request involving payload generation, injection testing, bypass construction, exploitation technique lookup, or offensive methodology reference
- Primary entry point: Root `README.md` for directory index, then navigate to named subdirectory
- Complements: SecLists (use SecLists for raw wordlists when PayloadsAllTheThings identifies the attack class)

## SecLists
- Path: `openclaw-skills/repos/SecLists/`
- Source: https://github.com/danielmiessler/SecLists
- Domain: Wordlists, fuzzing lists, enumeration lists, credential lists, discovery lists, payload lists, pattern matching lists
- Trigger conditions: Any request involving directory/file brute force, subdomain enumeration, username enumeration, password spraying, credential stuffing, fuzzing parameters, API endpoint discovery, common vulnerability pattern matching, default credentials lookup
- Primary entry point: Root directory — navigate by category: `Discovery/`, `Fuzzing/`, `Passwords/`, `Usernames/`, `Miscellaneous/`, `Pattern-Matching/`, `Payloads/`, `Web-Shells/`
- Complements: PayloadsAllTheThings (use PAT for the technique/exploit structure, SecLists for the raw list to feed into it)
