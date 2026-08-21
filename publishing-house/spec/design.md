# Publishing House Monorepo: Showroom, GitOps, and Ansible in a Single Repository

## Overview

This lab introduces the monorepo pattern for building and managing RHDP labs through Publishing House. Instead of spreading content, infrastructure configuration, and automation across multiple repositories, everything is versioned together in a single Git repository. Participants explore a pre-built example monorepo that combines Showroom lab content, Red Hat OpenShift GitOps resources, and Ansible automation — tracing how each piece connects and deploying the example environment to see the pattern in action.

## Target Audience

- **Role:** Lab authors and content developers building labs for the Red Hat Demo Platform
- **Experience level:** Beginner
- **What they already know:** Basic Git and command-line familiarity; general awareness of OpenShift as a platform
- **What they don't know:** How to structure a Publishing House project, how Showroom, GitOps, and Ansible collections fit together in a monorepo, and how Publishing House manages the full lab lifecycle

## Prerequisites

- Basic Git familiarity (clone, navigate a repository)
- No prior experience with Publishing House, Showroom, GitOps, or Ansible is required

<!-- Prerequisites are trust-based — the lab does not validate them automatically. -->

## Learning Objectives

1. Explore the structure of a Publishing House monorepo that integrates Showroom content, GitOps resources, and Ansible automation
2. Deploy lab infrastructure components using the GitOps and Ansible automation included in the monorepo

## Content Type

Lab (hands-on)

## Products & Technologies

- Red Hat OpenShift Container Platform
- Red Hat OpenShift GitOps (ArgoCD)
- Ansible (collections and CLI — not AAP Controller)
- Publishing House (RHDP internal lab delivery platform)
- Showroom (RHDP lab UI framework)

## Module Map

| Module | Title | Duration |
|--------|-------|----------|
| 1 | Exploring the Monorepo Structure | 20 min |
| 2 | Deploying with GitOps and Ansible | 20 min |
| — | **Total hands-on** | **40 min** |
| — | Intro / orientation | ~5 min |
| — | **Total lab** | **~45 min** |

## Difficulty Level

Beginner

## Environment

**Learner view:** Participants access a pre-configured OpenShift cluster with the example monorepo already cloned and available in their terminal. The repository contains all content, GitOps manifests, and Ansible collections in place. Participants navigate the repo, inspect the structure, and run provided commands — they are not building the monorepo from scratch.

**Automation needed:** Yes — the cluster must be provisioned and the example monorepo cloned and staged in the participant's environment before the lab starts.

## Infrastructure Requirements

- **Platform:** OCP
- **Cloud provider:** CNV
- **Cluster type:** SNO (Single Node OpenShift) — 1 node, 32 vCPU, 128GB RAM
- **OCP version:** 4.20
- **Topology:** Per-student
- **AAP:** Not deployed — Ansible used via collections and CLI only
- **AI/MaaS:** None
- **External services:** registry.redhat.io, quay.io, github.com
- **Non-GA products:** None

## Showroom Configuration

- **Pattern:** AgD v2 Open (`agd-open`) with `rhdp_showroom_theme`
- **Tabs:**
  - `>_ terminal` — bastion terminal via `/wetty`
  - `OCP Console` — `https://console-openshift-console.${DOMAIN}`

## GitOps Automation (`automation/gitops/bootstrap-infra/`)

Single Helm chart deployed by RHDP via `ocp4_workload_gitops_bootstrap`. Creates a `monorepo-demo` namespace as the demo GitOps target that participants observe syncing in ArgoCD during Module 2.

**ArgoCD pre-installed by RHDP** — `ocp4_workload_openshift_gitops` handles operator installation; bootstrap-infra assumes ArgoCD is already running.

**AgnosticV snippet:**
```yaml
ocp4_workload_gitops_bootstrap_repo_url: https://github.com/rhpds/ph-openshift-monorepo-example
ocp4_workload_gitops_bootstrap_repo_revision: main
ocp4_workload_gitops_bootstrap_repo_path: automation/gitops/bootstrap-infra
ocp4_workload_gitops_bootstrap_application_name: bootstrap-infra
ocp4_workload_gitops_bootstrap_helm_values: {}
```

## Ansible Automation (`automation/ansible/`)

Collection: `ph_openshift_monorepo_example.automation` — author `prakhar1985 <psrivast@redhat.com>`

**Roles:**
- `create_users` — Creates 4 Linux users (dev1–dev4) with password `rhdp@3456` on the bastion host using `ansible.builtin.user`
- `create_namespace` — Creates the `ansible_test_monorepo` namespace on OpenShift using `kubernetes.core.k8s`

**AgnosticV integration** — include the collection via `requirements_content` using the `#/path` fragment syntax:
```yaml
requirements_content:
  collections:
    - name: https://github.com/rhpds/ph-openshift-monorepo-example.git#/automation/ansible
      type: git
      version: main

workloads:
  - agnosticd.core_workloads.ocp4_workload_openshift_gitops
  - ph_openshift_monorepo_example.ansible.create_users
  - ph_openshift_monorepo_example.ansible.create_namespace
```

## Open Items Before Publishing

- `automation/ansible/playbooks/setup.yml` — referenced in Module 2 but not yet created; needs a simple playbook invoking the collection roles
- `automation/gitops/bootstrap-infra/application.yaml` — referenced in Module 2 Exercise 1; needs to be created so participants can apply it directly
- AgnosticV placeholders in Module 2 (`<your-repo>`, `<namespace>.<role_name>`) should be replaced with actual values before publication
