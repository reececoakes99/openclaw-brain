# OpenClaw Repo Index

## PayloadsAllTheThings

* **Path:** openclaw-skills/repos/PayloadsAllTheThings/
* **Source:** https://github.com/swisskyrepo/PayloadsAllTheThings
* **Domain:** Offensive security — payloads, exploitation techniques, injections,
 bypasses, privilege escalation, web attacks, network attacks, methodology
* **Trigger conditions:** Any request involving payload generation, injection testing,
 bypass construction, exploitation technique lookup, or offensive methodology reference
* **Primary entry point:** README.md at root, then navigate to named subdirectory
* **Skill handler:** skills/payload/payload-patts-lookup-v1/
* **Submodule:** Yes — full clone on disk

---

## SecLists

* **Path:** openclaw-skills/repos/SecLists/
* **Source:** https://github.com/danielmiessler/SecLists
* **Domain:** Wordlists for security testing — usernames, passwords, URLs, fuzzing
 strings, web shells, sensitive data patterns, discovery lists
* **Trigger conditions:** Any request involving directory brute-forcing, credential
 stuffing, fuzzing, enumeration, or wordlist-driven discovery
* **Primary entry point:** README.md at root — subdirectories organized by category
* **Key subdirectories:**
 * Discovery/Web-Content/ — directory and file brute-force lists
 * Passwords/ — credential lists
 * Usernames/ — username enumeration lists
 * Fuzzing/ — injection and fuzzing payloads
* **Submodule:** Yes — full clone on disk

---

## Adding New Repositories

Format for new entries:

## <Repository Name>
- Path: <relative-path-from-workspace-root>/
- Source: <GitHub URL>
- Domain: <domain-description>
- Trigger conditions: <when-to-use>
- Primary entry point: <file-path>
- Skill handler: <skill-path-if-applicable>
- Submodule: Yes/No
