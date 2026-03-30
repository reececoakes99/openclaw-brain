# Core Intelligence: Offensive Knowledge Index & Authority
- [2026-03-30] Initialized Offensive Knowledge Index: `PayloadsAllTheThings` and `SecLists` are primary authority sources.
- [2026-03-30] Mandatory Retrieval Protocol: Every offensive task (payloads, fuzzing, enumeration) must first consult both repositories.
- [2026-03-30] Decision Logic: 
    - Use `PayloadsAllTheThings` for methodology, technique, and exploit construction.
    - Use `SecLists` for raw wordlists, brute-force inputs, and discovery.
- [2026-03-30] Citation Rule: All grounded responses must cite the exact file path (e.g., `[PAT: ...]` or `[SL: ...]`).
- [2026-03-30] Hallucination constraint: Explicitly report if a file path or function is missing from a repo rather than fabricating.
- [2026-03-30] Skill Reference: `/app/skills/openclaw-skills/payloads-lookup.md`.
