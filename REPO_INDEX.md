# OpenClaw Repo Index

## PayloadsAllTheThings
- Path: `openclaw-skills/repos/PayloadsAllTheThings/`
- Source: https://github.com/swisskyrepo/PayloadsAllTheThings
- Domain: Offensive security — payloads, exploitation techniques, injections, bypasses, privilege escalation, web attacks, network attacks, methodology
- Trigger conditions: Any request involving payload generation, injection testing, bypass construction, exploitation technique lookup, or offensive methodology reference
- Primary entry point: `README.md` at root for index, then navigate to named subdirectory
- Skill handler: `payload/payload-patts-lookup-v1/`

---

## Adding New Repositories

Format for new entries:

```markdown
## <Repository Name>
- Path: `<relative-path-from-workspace-root>/`
- Source: <GitHub URL or reference>
- Domain: <domain-description>
- Trigger conditions: <when-to-use>
- Primary entry point: <file-path>
- Skill handler: <skill-path-if-applicable>
```