# System Design Starter

Turn a product idea—or an existing codebase—into a system design you can understand, adapt, and build from.

**System Design Starter** maps product needs to practical architecture: components, data, flows, tradeoffs, and a step-by-step path to a first version. It aims for clear explanations and a useful foundation without adding complexity for hypothetical scale.

## What it does

- Starts from a plain-language idea or inspects an existing codebase.
- Makes assumptions visible and asks focused questions only when they affect the design.
- Explains component responsibilities, data ownership, and important flows.
- Recommends technologies and databases with tradeoffs and current support references.
- Produces architecture, deployment, and database diagrams plus a prerequisite checklist.
- Generates both a machine-readable API schema and a human-readable API contract when an API is in scope.
- Maps cloud deployment stages from local development through staged production rollout and operations.
- Designs CI/CD stages for validation, immutable builds, environment promotion, approvals, observability, and rollback.
- Gives an implementation sequence and, when asked, can help scaffold the agreed foundation.

## Get the skill

The canonical copy is this repository: <https://github.com/Surya760/system-design-starter>. The skill instructions are in `SKILL.md`. The `agents/openai.yaml` file contains optional OpenAI interface metadata; Claude and Gemini can ignore it.

Choose the instructions below for the product you use. Installation makes a local or account copy of the skill; it does not automatically sync later changes from this GitHub repository. Reinstall or upload the updated copy after a new release.

## Use with OpenAI Codex

Codex supports personal skills and project skills. For a skill available in all your projects, clone this repository into your user skills folder:

```bash
git clone https://github.com/Surya760/system-design-starter.git \
  ~/.agents/skills/system-design-starter
```

For a skill shared with one codebase, run this command from that project's root instead:

```bash
git clone https://github.com/Surya760/system-design-starter.git \
  .agents/skills/system-design-starter
```

Codex-specific setups may also use `$CODEX_HOME/skills/` (usually `~/.codex/skills/`) for user skills. Start a new Codex session after installing, then invoke it with `$system-design-starter` or describe a matching design task. To update a cloned copy, run `git -C <skill-folder> pull`.

## Use with ChatGPT

ChatGPT's built-in Skills feature is available to eligible Business, Enterprise, Healthcare, and Edu accounts, subject to workspace settings. If the Skills page is unavailable, your account or workspace may not have access enabled.

1. Download this repository as a ZIP from GitHub using **Code → Download ZIP**.
2. In ChatGPT, open **Plugins → Skills → Create → Upload from your computer**.
3. Select the downloaded ZIP and wait for ChatGPT's scan to finish.
4. Enable the skill. Ask for a design directly, or say “Use System Design Starter” in your prompt.

For example:

> Use System Design Starter to design a first version of a neighborhood tool-lending app. I’m building it solo and want a low-cost stack. Include the database ERD, API contract files, cloud prerequisites, and staged deployment plan.

ChatGPT may automatically use an enabled skill when it matches your request. If your workspace does not allow uploads, ask its administrator about skill permissions. The uploaded copy will not automatically track GitHub changes.

## Use with Claude

### Claude Code

For a personal skill available in all projects, clone the repository into Claude Code's personal skills folder:

```bash
git clone https://github.com/Surya760/system-design-starter.git \
  ~/.claude/skills/system-design-starter
```

To share it with one codebase, clone it into that repository instead:

```bash
git clone https://github.com/Surya760/system-design-starter.git \
  .claude/skills/system-design-starter
```

Start or restart a Claude Code session. Invoke the skill with `/system-design-starter`, or ask Claude a matching question and let it select the skill automatically.

### Claude app

1. Download this repository as a ZIP from GitHub using **Code → Download ZIP**.
2. In Claude, open **Customize → Skills → + Create skill → Upload a skill**.
3. Upload the ZIP, then enable the skill in your Skills list.

Claude app Skills require **Code execution and file creation** to be enabled. They are documented for Free, Pro, Max, Ultra, Team, and Enterprise plans, subject to organization settings. On Team or Enterprise, sharing with coworkers may require an administrator to enable skill sharing. The uploaded copy will not automatically track GitHub changes.

## Use with Gemini

### Gemini Apps (web, mobile, and Mac app)

Gemini Apps can create a skill from a `SKILL.md` file or a folder containing it. To upload this repository:

1. Download this repository as a ZIP from GitHub using **Code → Download ZIP**, then unzip it. The extracted folder (usually named `system-design-starter-main`) should contain `SKILL.md` at its top level.
2. In Gemini, open **Customize → Skills**. If **Customize** is not visible, open **More** first.
3. Select **Create → Upload** and choose the extracted repository folder (or select its `SKILL.md` file if prompted).
4. Create or enable the skill. In a chat, invoke it with `/system-design-starter` (or `@system-design-starter` where that shortcut is available), or let Gemini select it automatically.

Gemini Skills availability depends on account and surface; the current help page lists Gemini web, mobile, and Mac app and requires users to be 18 or older. The uploaded copy will not automatically track GitHub changes.

### Gemini CLI

Install the public repository directly:

```bash
gemini skills install https://github.com/Surya760/system-design-starter
```

Start Gemini CLI and run `/skills` to confirm it is available. Invoke it by selecting the skill or ask a matching question. For local development, clone the repository into a recognized skills directory such as `.agents/skills/` in a project or `~/.gemini/skills/` for your user, then run `gemini skills link .` from the skill directory if you want to link that local copy.

## Buildable architecture and contract outputs

When an API is part of the system, ask for both artifacts: a machine-readable contract such as `openapi.yaml` and a readable `API_CONTRACT.md` covering endpoints, examples, auth, errors, retries, idempotency, and versioning. For GraphQL, gRPC, or event systems, it selects the matching schema format.

For cloud planning, it can produce an environment/deployment diagram, technology and service matrix, account and access prerequisites, stage gates, rollback plan, and operations checklist. It does not provision cloud resources unless you explicitly ask it to. Current support claims should be checked against official vendor docs.

For CI/CD planning, it can map pull request checks, build and artifact publication, staging verification, production promotion, security gates, required identities and secrets, and rollback. It treats a product's runtime data pipeline separately from the CI/CD pipeline that releases its code. For data systems, it also calls out replay, checkpoints, and reconciliation because reverting code does not undo data already written.

A generated project can include files such as:

```text
design/
  system-design.md
  API_CONTRACT.md
  openapi.yaml
  architecture.mmd
  deployment.mmd
  database-erd.mmd
```

The exact files depend on the project and the requested output. Unconfirmed product, scale, region, tax, and security decisions should appear as assumptions or open questions.

## Try it

**New idea:**

> Use System Design Starter to design a first version of a neighborhood tool-lending app. I’m building it solo and want a low-cost stack. Include the database ERD, API contract files, cloud prerequisites, and staged deployment plan.

**CI/CD and cloud deployment:**

> Design the GCP architecture and CI/CD release workflow for my daily learning-platform migration pipeline. Include the build and test stages, artifact registry, environment promotion, deployment approvals, secrets and identity setup, prerequisites, monitoring, and rollback. Explain separately how to replay or reconcile data if a release fails.

**Existing codebase:**

> Use System Design Starter to inspect this repository, explain its architecture, and show how to add team invitations.

**Continue into implementation:**

> Turn the agreed design into a starter project structure and implement the first milestone. Include the OpenAPI contract and human-readable API contract doc, deployment and database diagrams, and cloud setup prerequisites. Do not deploy anything yet.

For an existing project, run the agent from that project's workspace or give it the relevant files. A chat without repository access can still design from an idea or from files you attach.

## Public launch copy

**Short description:** From a rough idea to a system you can build.

**Announcement:** Have a product idea but aren’t sure how the pieces should fit together? System Design Starter turns a rough concept—or an existing codebase—into a clear architecture, data and request flows, practical tradeoffs, and a build sequence. It explains the choices so you can adapt the design and build your own foundation. Start small, keep the design understandable, and grow it when real needs call for it.

**One-line pitch:** A practical system design partner for your next project, from first idea to buildable plan.

## Scope

The design is a starting point, not a guarantee of production readiness, security, compliance, or capacity. Review critical decisions against the real requirements before launch.
