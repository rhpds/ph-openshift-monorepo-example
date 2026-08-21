# Editing Review — Module 02: Deploying with GitOps and Ansible

**Reviewed:** 2026-08-20  
**Reviewer:** AI (rhdp-publishing-house:module-reviewer)  
**Status:** Fixed

## Findings

### FIXED — C.6/D.8 (Medium): Em dash usage
**Line 33** — `Ansible executes tasks imperatively — in order — which makes it...`  
Em dashes not permitted by PH writing standards. Rewritten to use a comma clause instead.

### FIXED — C.9 (Warning): Title Case headings (9 headings)
All section headings converted from Title Case to sentence case per PH writing standards.
Proper nouns (Ansible, AgnosticV, GitOps) retain their capitalization.

| Line | Before | After |
|------|--------|-------|
| 13 | `Learning Objectives` | `Learning objectives` |
| 22 | `Introduction: How the Two Automation Layers Work Together` | `Introduction: how the two automation layers work together` |
| 124 | `Exercise 2: Running Ansible Automation` | `Exercise 2: running Ansible automation` |
| 184 | `Exercise 3: Verifying the Deployed Environment` | `Exercise 3: verifying the deployed environment` |
| 249 | `AgnosticV Integration` | `AgnosticV integration` |
| 254 | `Including the Ansible Collection` | `Including the Ansible collection` |
| 272 | `Referencing Collection Roles as Workloads` | `Referencing collection roles as workloads` |
| 284 | `Wiring in the GitOps Layer` | `Wiring in the GitOps layer` |
| 299 | `Learning Outcomes Checkpoint` | `Learning outcomes checkpoint` |

### FIXED — Prose (author request): simplify verbose sections
- Ansible intro paragraph (lines 31-33): tightened from 3 sentences to 2; removed generic responsibility list
- Conclusion: removed final redundant sentence ("Everything a lab needs...")

### FIXED — Placeholders: AgnosticV repo and role references
- `<your-repo>` → `ph-openshift-monorepo-example`
- `<namespace>.ansible.<role_name>` → `ph_openshift_monorepo_example.ansible.create_users`

## Spec Alignment

| Check | Result | Notes |
|-------|--------|-------|
| SA-1: Outline coverage | PASS | All 3 exercises + AgnosticV section present |
| SA-2: Learning objectives match | PASS | 4 objectives, all covered in exercises |
| SA-3: Duration alignment | PASS | 3 exercises fits 20 min |
| RS-1: Product name accuracy | PASS | ArgoCD, Ansible, OpenShift used correctly |
| RS-2: Version consistency | PASS | No hardcoded OCP version strings |
