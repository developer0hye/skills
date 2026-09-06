# Figure sets and document integration

Use when the requested work includes placement planning, insertion, or replacement. Existing authorization for the specified document action is sufficient; this skill adds no confirmation requirement.

## Identity and ordering

Maintain separate fields for:

`asset_id | prompt_revision | output_path | review_status | document_figure_number | caption | insertion_anchor`

Add published version and remote media ID after publication when available. Asset IDs identify files and generations; document numbers follow final reading order. Do not rename assets merely to match captions. Usually keep numbers in document captions so reordering does not require raster regeneration.

Place an overview early. Put detailed figures after the concepts required to read them, near their explanation. Specify a heading plus before/after relation to a paragraph/table rather than only a section number that may change. Use one caption format and update cross-references with numbering.

If manual insertion markers are requested, make each a short removable paragraph at the exact planned location. Remove it after insertion. Do not leave planning instructions mixed into final prose.

## Publishing and replacement

- Fetch the current document and retain a before snapshot. Respect remote version/concurrency controls and document instructions.
- Match every caption to the reviewed file. An uploaded attachment does not prove the body references it. For replacement, verify inline media points to the revised asset; the same filename alone proves nothing.
- Prefer focused mutations. If only full-body replacement works, preserve unrelated content and links, compare the proposed change, and use a version guard. Do not delete historical attachments just because inline references changed.
- Read back the published version. Check count, caption sequence, media mapping, cross-references, and unrelated text preservation. Inspect rendered placement/readability when available; describe verification limits otherwise.
- When remote downloads are available and byte identity matters, compare hashes with reviewed local originals. Hash matching verifies asset identity, not technical correctness or rendered layout.

Report what actually reached the destination, including saved version when available. Keep prompt revision, image review, attachment upload, inline insertion, and publication distinct.
