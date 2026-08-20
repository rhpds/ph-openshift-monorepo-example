# Module 01 — Exploring the Monorepo Structure

### Brief Overview

This module introduces participants to the Publishing House monorepo pattern by walking them through a pre-built example repository. Participants trace how Showroom lab content, Red Hat OpenShift GitOps resources, and Ansible automation are organized together in a single Git repository. By the end of the module, participants understand why the monorepo approach is used and can identify the role of each major directory in the project.

### Audience and Time

- **Target personas:** Lab authors and content developers building labs for the Red Hat Demo Platform
- **Experience level:** Beginner — no prior experience with Publishing House, Showroom, GitOps, or Ansible required
- **Prerequisites for this module:** Basic Git familiarity (clone, navigate a repository); access to a pre-configured OpenShift cluster with the example monorepo already cloned and staged in the terminal
- **Estimated duration:** 20 minutes

### Learning Objectives

- Identify the top-level directories of a Publishing House monorepo and explain the purpose of each
- Locate and describe the Showroom content layer, including the Antora component descriptor and lab pages
- Locate and describe the GitOps resources included in the monorepo
- Locate and describe the Ansible automation collection included in the monorepo
- Explain how versioning all three layers together in a single repository benefits lab lifecycle management

### Lab Structure

| Section | Title | Duration |
|---------|-------|----------|
| 1 | Introduction: What Is the Monorepo Pattern? | 3 min |
| 2 | Navigating the Top-Level Repository Structure | 5 min |
| 3 | Examining the Showroom Content Layer | 4 min |
| 4 | Examining the GitOps Resources | 4 min |
| 5 | Examining the Ansible Automation | 4 min |

### Detailed Steps

1. Read the brief orientation text explaining why Publishing House uses a monorepo to co-locate Showroom content, GitOps manifests, and Ansible collections.
2. In the terminal, navigate to the root of the pre-cloned example monorepo.
3. List the top-level directories and observe the high-level layout of the repository.
4. Review any top-level README or documentation file that describes the purpose of each directory.
5. Navigate into the Showroom content directory and inspect its structure, including the Antora component descriptor and the module pages directory.
6. Open the Antora component descriptor and identify the component name, version, and navigation reference.
7. Browse the lab pages to see how the content is organized into modules and pages.
8. Navigate into the GitOps resources directory and list its contents.
9. Identify the Helm chart or ArgoCD application manifests present and note the resources they define.
10. Navigate into the Ansible automation directory and list its contents.
11. Identify the collection structure, noting any roles, playbooks, or inventory files present.
12. Return to the repository root and reflect on how all three layers — content, GitOps, and Ansible — are versioned together and cross-reference one another.

### Key Takeaways

- A Publishing House monorepo stores Showroom lab content, OpenShift GitOps resources, and Ansible automation in a single repository so that all layers are versioned and released together.
- The Showroom content layer uses Antora conventions: a component descriptor and a modules directory containing AsciiDoc pages.
- The GitOps layer contains OpenShift manifests (Helm charts and/or ArgoCD applications) that automate cluster-level resource provisioning.
- The Ansible layer contains a collection with roles and playbooks that complement the GitOps automation.
- Co-locating all layers simplifies change management: a single pull request can update content, infrastructure, and automation simultaneously.
