# ph-openshift-monorepo-example

This hands-on lab introduces a monorepo-based approach for building and managing technical labs through Publishing House.

Participants will work from a single Git repository that contains the lab content, Showroom configuration, GitOps resources, Ansible automation, and the Ansible collections required by the lab. Instead of maintaining content and automation across multiple repositories, the complete lab lifecycle is managed and versioned together.

During the lab, participants will use Publishing House to scaffold the lab structure, build the learner experience with Showroom, deploy required platform components through GitOps, and use Ansible collections from the same repository to configure and prepare the environment.

The lab demonstrates how a monorepo can simplify development, testing, versioning, and ongoing maintenance while still keeping clear boundaries between content, infrastructure configuration, and automation. Participants will leave with a practical understanding of how Publishing House can provide a repeatable development workflow for labs that need Showroom, GitOps, and Ansible working together.


**Owner:** prakhar1985

---

## What was set up

1. Repository created
2. `catalog-info.yaml` added to repository
3. Registered in Developer Hub catalog
4. Orchestrator workflow started — your AI-guided content pipeline is running!

## What happens next

Claude will walk you through the entire content lifecycle — from intake and spec creation, through Jira tracking and reviews, all the way to a published lab on RHDP. Just follow the prompts!

## Getting started

### DevSpaces (recommended)

1. Open in DevSpaces: `https://devspaces.apps.ocpv-infra02.wdc07.infra.demo.redhat.com#https://github.com/rhpds/ph-openshift-monorepo-example`
2. Use Claude via the **extension** or the **CLI**:
   - **Extension:** Click the **Claude** icon in the sidebar, click **New Session**. If the Claude icon is not visible, open **Extensions** (`Ctrl/Cmd+Shift+X`), find **Claude Code for VS Code** under the DevSpaces section, click it, then click **Enable (Workspace)**.
   - **CLI:** Open a terminal and run `claude`
3. Run `/rhdp-publishing-house` — and you're off!

### Local machine

1. Install the skills:
   ```
   git clone -b prod https://github.com/rhpds/rhdp-publishing-house-skills.git ~/.claude/skills/publishing-house
   ```
2. Clone the repo:
   ```
   git clone https://github.com/rhpds/ph-openshift-monorepo-example
   ```
3. `cd ph-openshift-monorepo-example`
4. Start Claude CLI: `claude`
5. Run `/rhdp-publishing-house` — and you're off!
