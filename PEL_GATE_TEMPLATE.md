# PEL_GATE_TEMPLATE.md
## Pathos / Ethos / Logos Approval Gate

This template is filled in by the receiving agent at the end of Phase 6 (Build sequence).
The Architect (Sage) is the SOLE issuer of the final verdict.
Agent never issues self-verdict. Agent fills the document, surfaces it, waits.

Format derived from /mnt/project/pathos_ethos_logos_approval_gate.md (private, do not expose).
The PEL term itself is renamed in public docs to "approval_gate" but stays as PEL internally for clarity with the Architect.

---

## Header (agent fills)

- Build version: v0.1.0
- Build date: ____
- Receiving agent identity: Claude Code CLI / Codex CLI / [other], model: ____
- Source session reference: this Claude.ai project, opus 4.7, turns 1 through N
- Architect: Sage
- Q-decisions used:
  - Q1 (attribution): ____ (architect-decided | default-b)
  - Q2 (license): ____ (architect-decided | default-a)
  - Q3 (must-haves): ____ (architect-decided | default-six-as-listed)
- Appendix B status: ____ (resolved with URLs | partially resolved | deferred to v0.2)

---

## Section 1: Pathos (mission and execution)

Agent answers each. Honest only. No claims of completion that are not true.

### 1.1 Was the stated mission accomplished?

Mission per HANDOFF_PACKET section 1: ship CE_RD_OS v0.1 as dual-track artifact (GitHub repo + 10-file text zip), privacy clean, presentable, grant-application ready.

Agent claim: ____ (yes | partially | no)

Evidence:
- GitHub repo state: ____ (path or URL)
- Text bundle zip path: ____
- Files shipped: ____ count
- Files deferred: ____ count
- verify_self.sh exit code: ____
- pack_text_bundle.sh exit code: ____

### 1.2 Did the agent operate within the stated scope?

- Track A only: ____ (yes | leakage detected | unsure)
- Track B exclusion verified: ____ (yes | leakage detected)
- Mercor exclusion verified: ____ (yes | leakage detected)
- Internal codename exclusion verified: ____ (yes | leakage detected)
- 143_protocol rename applied: ____ (yes | partial | no)
- sonnet rename applied: ____ (yes | partial | no)
- Q1/Q2/Q3 decisions logged: ____ (yes | no)

If any "no" or "leakage detected" - agent stops and writes a remediation plan in section 4.

### 1.3 What did the agent NOT do?

Agent lists explicitly. Honesty required. Examples:
- Did not implement the GEPA backend (out of scope per Q3 default)
- Did not resolve [list] Appendix B gaps (deferred to v0.2)
- Did not push to public remote (waiting on this gate)
- Did not [other]

---

## Section 2: Ethos (sources and evidence)

### 2.1 Source hierarchy compliance

Per system_directive: arXiv, official documentation, auditable repos, institutional/lab/military, official user docs only.

Agent confirms ALL citations in the bundle fall within this hierarchy:
____ (yes | exceptions listed below)

Exceptions (if any):
- File: ____ Source: ____ Reason for non-Tier-1: ____ Architect approval needed: ____

### 2.2 Citation verification

For each claim in README.md, AGENTS.md, and references/:
- Citations present: ____ (count)
- Citations broken (404): ____ (count - rerun a link checker)
- Citations to retracted papers: ____ (count)
- Citations to non-Tier-1 sources without Architect approval: ____ (count - must be 0)

### 2.3 Quote and paraphrase compliance

Per copyright requirements:
- Direct quotes per source: must be max 1, under 14 words, in quotation marks
- Paraphrase-first: must be the dominant pattern
- No long (30+ word) summaries of any one source

Agent confirms compliance: ____ (yes | violations listed)

### 2.4 License attribution

For every incorporated pattern or named tool:
- Compound Engineering plugin pattern: cited as MIT / EveryInc reference, no code copied: ____
- agentskills.io spec: cited as Apache 2.0 / CC-BY-4.0: ____
- AGENTS.md spec: cited as Linux Foundation Agentic AI Foundation: ____
- RaR paper: cited as arXiv:2507.17746: ____
- GEPA paper + repo: cited as arXiv:2507.19457 + Apache 2.0: ____
- Letta architecture: cited as Apache 2.0 reference, no code copied: ____
- All other sources: ____

### 2.5 Privacy gate (verify_self.sh) result

Final run output (last execution):
```
[paste verify_self.sh stdout here]
```

Exit code: ____
Hits: ____ (must be 0 for green light)

---

## Section 3: Logos (rubric evaluation)

The Trinity 3x3 rubric applied to the bundle itself.

Score each cell 0 (fail) or 1 (pass) for boolean mode.
For scaled mode, 0.0 to 1.0.

### 3.1 The 9-cell grid

|  | Coverage | Self-contained | Importance |
|---|---|---|---|
| Pathos (mission) | __ | __ | __ |
| Ethos (sources) | __ | __ | __ |
| Logos (rubric) | __ | __ | __ |

### 3.2 Cell rationales (one sentence each, no jargon, no displacive summaries)

- Pathos-Coverage: ____
- Pathos-Self-contained: ____
- Pathos-Importance: ____
- Ethos-Coverage: ____
- Ethos-Self-contained: ____
- Ethos-Importance: ____
- Logos-Coverage: ____
- Logos-Self-contained: ____
- Logos-Importance: ____

### 3.3 Aggregate

- Boolean mode threshold: 9/9 must pass for green light
- If any cell scores 0: agent does NOT issue green light, lists remediation in section 4

Aggregate result: ____ (9/9 PASS | sub-9, remediation needed)

### 3.4 Compound Engineering 14-reviewer pass results (if Step 6.3 was run)

- Total findings: ____
- P0 (blocking): ____
- P1 (important): ____
- P2 (nice-to-have): ____
- All P0 resolved: ____
- All P1 resolved or explicitly deferred to v0.2: ____

If P0 or unresolved P1 remain - agent does NOT issue green light.

---

## Section 4: Remediation plan (if any section above showed a deficit)

For each deficit found in sections 1, 2, or 3:

| Deficit | Severity | Proposed fix | Effort estimate | Architect input needed |
|---|---|---|---|---|
| ____ | ____ | ____ | ____ | ____ |

If the remediation plan is non-empty: agent loops back to BUILD_SEQUENCE Phase 6, fixes, re-runs verify_self.sh, re-fills sections 1, 2, 3, then re-submits this gate.

---

## Section 5: Hand-off summary for Architect

One paragraph, max 6 sentences. No emdashes. Architect reads this first.

Template:
> CE_RD_OS v0.1 build is at [PHASE]. Q-decisions: [Q1=__, Q2=__, Q3=__].
> Privacy gate: [PASSED | FAILED]. Trinity rubric: [9/9 | sub-9].
> [N] files shipped, [M] deferred to v0.2.
> Recommended verdict: [APPROVE | REVISIONS | REJECT].
> Specific items needing Architect attention: [list, max 3].
> Awaiting verdict before [push to public remote | continuation handoff].

Agent fills:
> ____

---

## Section 6: Architect verdict (Architect-only)

DO NOT FILL. Architect fills.

- [ ] APPROVED: Agent proceeds to BUILD_SEQUENCE Step 7.3 APPROVED path, pushes to public remote, publishes release.
- [ ] REVISIONS: Architect lists revisions below. Agent loops to Phase 6, applies, re-submits.
- [ ] REJECTED: Architect provides reason. Agent packages state into HANDOFF_PACKET_v2.md, surfaces, stops.

Architect signature line:
- Verdict: ____
- Architect identity verified: ____ (3ztz / ztz3)
- Date: ____
- Conditions or revisions (if any): ____

---

## Section 7: Build log (append-only)

Each verify_self.sh run, each major decision, each Architect interaction logged here for audit.

```
[YYYY-MM-DD HH:MM] [actor] [event]
```

Initialize with the receiving session start time.

---

End PEL_GATE_TEMPLATE v1.
