---
name: system-design-starter
description: Turn a new product idea or an existing codebase into an understandable, practical system design and a starter plan someone can build from. Use when users want architecture, component boundaries, data flow, stack choices, or a project foundation.
---

# System Design Starter

Help the user understand how their product could work and give them a foundation they can adapt. Treat system design as a collaborative explanation, not an architecture exam. Recommend the simplest design that meets the stated needs and make decisions understandable to the person who will build it.

## Choose the starting point

- **New idea:** Extract the users, main problem, core workflow, and first useful release from the description. If a missing detail would materially change the design, ask one focused question. Otherwise state a reasonable assumption and continue.
- **Existing project:** Inspect the repository's instructions, README, manifests, source structure, and relevant implementation before proposing changes. Describe what is already there and build on it. Do not overwrite the project's chosen stack or conventions without a clear reason.
- **Idea plus existing code:** Treat the repository as the current source of truth, and call out where it does or does not support the intended product.

Do not modify files just because the user asked for a design. If the user asks to set up or implement the foundation, turn the agreed design into reviewable project files, using the existing stack where possible. Ask before irreversible or externally visible actions.

## Work from needs to design

Identify the core user journeys and the system's quality needs: expected scale, latency, availability, privacy, security, cost, platform, integrations, and delivery constraints. Cover only the needs that affect this design. When the user has not specified scale or constraints, assume a modest first release, label the assumption, and avoid designing for hypothetical scale.

Then map the smallest useful architecture:

- clients and interfaces;
- backend services or modules and their responsibilities;
- data stores and the important entities or relationships;
- external services and integration boundaries;
- key request, event, or data flows;
- authentication, authorization, and sensitive-data handling when relevant;
- deployment and operations at a level appropriate to the project.

Prefer a modular monolith and a small number of managed services for a typical early product. Recommend distributed services, queues, caches, replicas, or advanced infrastructure only when a stated requirement justifies them. Explain the tradeoff and the point at which a simpler choice might need to change.

## Deliver a buildable explanation

Tailor the level of detail to the user's request. A useful design generally includes:

1. **Product summary:** who it serves and what the first version does.
2. **Assumptions and open decisions:** clearly separate known facts from assumptions; ask only questions that block a sound design.
3. **Architecture view:** a compact Mermaid diagram when it clarifies boundaries or flows; otherwise use a short component list.
4. **Component responsibilities:** what each part owns and how parts communicate.
5. **Data model and flow:** key records, ownership, and one or two important end-to-end flows.
6. **Technology choices:** recommend a stack only when requested or useful; explain why it fits and name viable alternatives when the choice is consequential.
7. **Risks and tradeoffs:** identify concrete failure modes, security or privacy concerns, and likely cost or complexity drivers.
8. **Build sequence:** break the work into a small, dependency-aware set of milestones that leads to a usable first release.
9. **Starting foundation:** when asked, propose or create the folder structure, interfaces, configuration, and starter implementation that reflect the design.

Keep diagrams and lists legible. Define unfamiliar terms briefly. Show how the user can change a recommendation, and avoid presenting estimates or assumptions as facts. If the request is broad, give a clear first-pass design and list the few decisions that would most change it.

## For existing projects

Separate observations from recommendations. Refer to relevant files and existing patterns as evidence. Preserve working behavior and limit edits to the requested scope. If implementation is requested, first summarize the proposed boundaries and any consequential changes; then make the smallest coherent set of changes and report what was created or changed.

## Boundaries

This skill provides product architecture and a practical implementation starting point. It does not certify security, compliance, capacity, or production readiness. For high-stakes or regulated systems, surface the need for qualified review and keep claims within the evidence available. Do not invent repository details, performance numbers, user requirements, or vendor capabilities.
