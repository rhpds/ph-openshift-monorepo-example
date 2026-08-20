# Module 02 — Deploying with GitOps and Ansible

### Brief Overview

This module gives participants hands-on experience deploying the example lab environment using the GitOps and Ansible automation bundled in the monorepo. Participants run provided commands against a pre-configured OpenShift cluster to apply GitOps resources via Red Hat OpenShift GitOps (ArgoCD) and execute Ansible automation from the collection included in the repository. The goal is to see the two automation layers work together as part of a single, versioned lab delivery workflow.

### Audience and Time

- **Target personas:** Lab authors and content developers building labs for the Red Hat Demo Platform
- **Experience level:** Beginner — no prior experience with GitOps or Ansible is required
- **Prerequisites for this module:** Completion of Module 01 (Exploring the Monorepo Structure); access to the pre-configured OpenShift cluster with the example monorepo already cloned and staged in the terminal
- **Estimated duration:** 20 minutes

### Learning Objectives

- Deploy lab infrastructure components by applying the GitOps resources included in the monorepo
- Execute Ansible automation from the monorepo collection to configure the lab environment
- Observe how the GitOps and Ansible layers complement each other in a Publishing House lab delivery workflow
- Verify that deployed resources are in the expected state after automation completes

### Lab Structure

| Section | Title | Duration |
|---------|-------|----------|
| 1 | Introduction: How the Two Automation Layers Work Together | 3 min |
| 2 | Deploying with Red Hat OpenShift GitOps (ArgoCD) | 8 min |
| 3 | Running Ansible Automation | 7 min |
| 4 | Verifying the Deployed Environment | 2 min |

### Detailed Steps

1. Read the brief orientation text explaining how GitOps and Ansible complement each other in this monorepo: GitOps manages cluster-level resources declaratively; Ansible handles configuration and orchestration tasks that fall outside GitOps scope.
2. In the terminal, confirm you are at the root of the example monorepo and that the pre-configured OpenShift cluster is reachable.
3. Navigate into the GitOps resources directory identified in Module 01.
4. Run the provided command to apply the GitOps resources to the cluster (the exact command is provided in the lab instructions — participants are not expected to construct it themselves).
5. Observe the output to confirm that ArgoCD has received and is reconciling the application manifests.
6. Open the ArgoCD console URL provided in the lab environment and verify that the application appears and reaches a synced, healthy state.
7. Return to the terminal and navigate into the Ansible automation directory identified in Module 01.
8. Run the provided Ansible command to execute the automation playbook against the lab environment.
9. Observe the Ansible output, noting each task as it runs and confirming there are no failures.
10. After automation completes, run the provided verification command to confirm that all deployed resources are in the expected state.
11. Review what was provisioned by each layer — GitOps resources versus Ansible-configured components — and note how the two layers divided responsibility.

### Key Takeaways

- Red Hat OpenShift GitOps (ArgoCD) continuously reconciles cluster state against the manifests stored in the monorepo, providing declarative, auditable infrastructure management.
- Ansible automation handles configuration tasks that complement the GitOps layer, such as bootstrapping application state or configuring external integrations.
- Both automation layers are version-controlled in the same repository as the lab content, so content updates and infrastructure updates can ship together.
- Participants deploy the environment by running provided commands — the monorepo pattern means everything needed is already in place; no separate setup repository is required.
- Verifying deployed resources confirms the end-to-end automation chain is working as designed.
