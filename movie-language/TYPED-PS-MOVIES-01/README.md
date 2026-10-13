# TYPED-PS-MOVIES-01 — Dependently typed mathematical movies

Planning result, 2026-10-13. Primary project: isomorphisms/hatcher.

A movie program should state what is constructed and which relationships its movement preserves. Its figures, labels, controls and rendered frames must follow from that construction.

**Decision:** build an Idriç-integrated language as a library with a small checked scene description. Keep mathematical construction, geometric representation, motion, numerical lowering and drawing distinct. Emit PostScript first and add native framebuffer and shader consumers through the same boundary.

This is an implementable design and job packet. No new compiler proof, rendered movie, GPU execution or physical-device acceptance is claimed by this planning result.

## Eight deliverables

1. [Requirements](requirements.md)
2. [Architecture and language decision](architecture.md)
3. [Core types and proof obligations](core-types.md)
4. [Examples and invalid cases](examples.md)
5. [Execution, interaction and export](execution.md)
6. [Reference study](references.md)
7. [Implementation plan](implementation-plan.md)
8. [Nine complete Sun jobs](jobs.md)

[Source state](source-state.tsv) binds the repository observations. [Planning receipt](receipt.tsv) distinguishes source inspection and design from implementation evidence.

The recovered original assignment proposed twelve boundaries and requested 8–12 Sun jobs. The nine jobs retain all twelve boundaries, combining objects with geometry, time with transformations, and the book example with its linked controls. The current request adds all ten animation references and explicit comparison with Idris 2, Agda and Rocq.

The original prompt was recovered through requirement summaries, not an authoritative verbatim transcript. This packet preserves the recovered requirements and the user's current corrections; it does not present itself as a copy of that original prompt.
