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
