---
name: grounded-technical-figures
description: Create, revise, and review image-generation prompts and technical figures grounded in source code, specifications, or research. Use for implementation diagrams, model training and inference figures, data transformations, and technical-document figure sets where correct visual semantics matter.
---

# Grounded Technical Figures

Turn verified behavior into figures that remain correct without the surrounding conversation. Apply across products and domains: software architecture, ML, data pipelines, scientific methods, and operational workflows. Do not carry a previous project's class names, architecture, colors, versions, or scene into a new project as facts.

## Keep this reusable skill free of private project content

Store only general methods and synthetic, domain-neutral examples in this skill and its supporting files. Do not copy company/customer names, private URLs, repository identities, internal paths, source excerpts, credentials, screenshots, real datasets, or proprietary architecture, configuration, measurements, and release details into the skill. Removing names alone is insufficient if an example still reveals a distinctive internal implementation.

Keep task-specific evidence, prompts, images, and manifests in the authorized project workspace; do not bundle or link them as skill resources. Before updating or sharing the skill, inspect every packaged file, including metadata and examples, for identifying details and substantive private content. Preserve reusable lessons through abstraction, not through anonymized copies of internal material.

Match the requested deliverable: prompt drafting, generation, review, or document insertion. Prompt requests alone do not authorize generation or external publication. Use the user's chosen generation surface when available. For generation/editing, follow the available image-generation tool or skill's instructions; this skill supplies content and verification, not a replacement tool protocol. Suggest code/vector diagrams when materially more suitable, while preserving an explicit request to use an image model.

## Establish facts before the picture

1. Identify the intended reader and the one question each figure should answer. Read the target document and relevant sources, not just module names or a previous prompt.
2. Record source revision/configuration and evidence for consequential claims. Trace calls, guards, data objects, transforms, state changes, and outputs. Separate implemented capability, default configuration, user-reported operational use, observed deployment, and illustrative examples. Mark unresolved claims rather than inventing a definitive diagram.
3. Write a small node/edge contract before prose styling. For each important arrow record source, destination, carried object or meaning, condition, and branch outcome. Distinguish data flow, execution order, supervision, comparison, and artifact provenance. A function call sequence does not necessarily mean an image tensor passes through every box.
4. Verify exact identifiers, units, shapes, inequalities, and the target of each filter. Separate class schema from enabled classes, training from inference, and source-level behavior from exported-artifact behavior. An output not returned does not prove graph pruning; matching filenames do not prove artifact identity.

Keep evidence alongside the project, outside visible figure text. A compact record can use `claim | source revision + location | configuration/scope | certainty | visual implication`.

## Design the explanation

- Put the overview before detailed mechanisms. Introduce terms before dense diagrams. Give each figure a distinct purpose; use a comparison table, transformation sequence, or timeline when a flowchart would imply false execution order.
- Prefer explicit, short edges over tangled branches. For repeatedly misrendered optional paths, put active and bypass cases in disconnected panels. A bypass must terminate at the actual retained/pass-through result.
- Distinguish input data, annotation views, intermediate representations, outputs, and legends. A legend is not a processing node. Supervision arrows must not make painted annotations look like model input unless they actually are.
- Depict the actual data modality and unit: full frame, local crop, patch, document page, waveform, etc. When photographic realism matters, apply it to scene interiors while keeping modules and typography clean. Do not force photographs into symbolic data or diagrams without image inputs.
- For geometric transformations, use one reference scene, known coordinates and transform parameters. Do not imply an exact crop by redrawing a similar scene. See [failure-patterns.md](references/failure-patterns.md) for geometry and branch pitfalls.
- Use conventional terms from the relevant technical field while preserving exact code identifiers where they matter. Do not invent paper-like jargon or rename a class for elegance.

## Write standalone prompts

Use [prompt-contract.md](references/prompt-contract.md) when drafting or revising prompts. Put purpose, required structure and exact visible labels first; append the same complete shared style block to every prompt. Separate visible text from construction instructions and private review checks. Resolve contradictions such as demanding pixel accuracy while labeling the same geometry “not to scale.”

For a set, maintain stable asset IDs, individual full prompts, and a small manifest. If a master Markdown repeats prompts, synchronize it with actual submitted text. Include shared style in every prompt; “same style as above” is insufficient across independent chats. Match an accepted reference image when supported, since repeated wording alone does not guarantee consistency.

## Generate and verify actual outputs

- For a new set, generate and inspect a representative figure before scaling up. For an established approved set, work on requested figures without reopening settled choices.
- A sent prompt, tool success, downloaded file, or generator self-check is not an accuracy review. Inspect the actual full-resolution output and readability at intended document size. Trace consequential arrows and inspect text, geometry, inputs, and branch outcomes against the contract.
- Review structural correctness before appearance. Read [failure-patterns.md](references/failure-patterns.md) for known mechanisms and targeted repairs.
- Make local corrections explicit: identify the wrong node/edge/region, specify the replacement, and preserve approved content. Inspect the whole edited result for regressions. Stop repeating a failed prompt; simplify or change representation when the model cannot preserve the contract. Disclose unresolved limitations instead of approving the image.
- Keep `prompt revised`, `submitted`, `generated`, `reviewed`, and `published` distinct. Save final originals together with prompt revision and review status. Preserve superseded outputs separately when useful for comparison.

## Integrate when requested

Read [document-integration.md](references/document-integration.md) when placing or replacing figures. Stable generation IDs are not document figure numbers. Number captions in reading order after placement, and verify the saved document rather than inferring success from an upload response.
