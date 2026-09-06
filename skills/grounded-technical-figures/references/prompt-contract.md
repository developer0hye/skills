# A prompt contract for technical figures

Use the sections needed by the figure. Resolve placeholders into concrete values before sending. The contract can describe software, ML, physical processes, or research methods.

## Preparation record

Keep alongside the prompt, usually outside the generator input:

- Stable asset ID and prompt revision.
- Reader's question and the explanation the figure must support.
- Verified sources and scope; uncertain claims omitted or visibly qualified.
- Nodes and exact edges, including the meaning/type of each connection.
- Exact labels, formulas, units, and sample values; identify hypothetical values.
- Required input/output examples and their granularity.
- Document position relative to an actual heading or paragraph.
- A few decisive checks observable in the rendered image.

## Standalone English prompt pattern

```text
Generate ONE technical figure titled "[title]".
Purpose: [one explanatory claim].
Scope caption: "[revision/configuration qualification readers need]".

REQUIRED STRUCTURE
[Panel count, reading order, and each panel's role.]
[Exact node labels and required connections. Identify alternative panels
that must remain disconnected. State the object carried by each key edge.]

VISIBLE CONTENT
[Exact titles, labels, comparison rows, formulas, notes, and legend entries.]
[Differentiate measured results from illustrative values.]

INPUT AND TRANSFORMATION CONTENT
[Actual modality, object, and unit: whole frame, patch, signal, document, etc.]
[When needed: one reference scene, fixed crop/mask coordinates, resize method,
padding, and content that must remain identical across panels.]
[Annotation views, clean inputs, and outputs have distinct roles.]

CONSTRUCTION ONLY — DO NOT RENDER AS TEXT
[Layout constraints and routing. Short node IDs only if helpful.]
Only designated titles, labels, captions, notes, table cells, and legend
entries may appear as text. Do not print layout ratios, node IDs, reasoning,
or review instructions. Do not create additional edges or numerical claims.

SHARED STYLE — RENDERING INSTRUCTIONS ONLY
[Insert the COMPLETE identical project style block, not a reference to it.]

PRIVATE RENDER CHECKS — DO NOT PRINT
[Figure-specific checks of actual arrows, labels, geometry, and inputs.]
Return one image. These instructions do not replace external review of the
generated result.
```

Put semantics ahead of decoration. Compress redundant prose rather than hiding technical requirements after long stylistic instructions. In chat workflows, provide the full prompt in the message when practical; do not assume a TXT attachment was used merely because it uploaded. If separate chats were requested, keep one figure per chat and record the mapping.

## Adaptable shared style example

This is a starting point, not a universal branding rule. Adapt to the project, then repeat the exact block in each standalone prompt.

```text
Landscape 16:9 technical-report figure on white. Consistent sans-serif type,
dark navy text, generous whitespace, thin outlines and restrained pale module
fills. Use one stable semantic color mapping across the set, with labels or
line styles so meaning does not depend on color alone. Clearly separated
panels; short connectors with explicit arrowheads. No decorative 3D effects.
Use typography sized for the figure's final reading width. Keep technical
modules flat and clean. Where photographic data examples are specified,
make only their interiors photorealistic and faithful to the data modality,
viewpoint, scale, and input granularity. Corresponding transformation panels
reuse the same scene and objects. Label synthetic examples as synthetic;
do not imply they are customer data or measured experimental results.
Print only explicitly designated visible text. Preserve exact identifiers,
units, and formulas. Technical meaning takes priority over decoration.
```

## Local edit pattern

```text
Edit the supplied figure. The defect is [specific visible mismatch].
Replace [exact node/edge/region] with [desired observable arrangement].
Remove [specific wrong connector or content].
Keep [approved text, scene geometry, branches, style] unchanged.
Check [critical condition] and ensure the edit introduced no new arrows,
labels, or changes elsewhere. Return one corrected complete figure.
```

When exact geometry repeatedly fails, do not add ever longer contradictory instructions. Reduce the example, remove duplicated transformed thumbnails, or use a verified reference rendering when permitted. If exact pixel correspondence cannot be achieved with the chosen tool, label the result honestly as schematic and avoid claiming numerical geometric fidelity. Use deterministic construction only when the user's requested tool scope permits it; follow image-editing tool restrictions.
