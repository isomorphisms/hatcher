# TYPED-PS-MOVIES-01 — Dependently typed mathematical movies

Planning result, 2026-10-13. Primary project: isomorphisms/hatcher.

A movie program should state what is constructed and which relationships its movement preserves. Its figures, labels, controls and rendered frames must follow from that construction.

**Decision:** build an Idriç-integrated language as a library with a small checked scene description. Keep mathematical construction, geometric representation, motion, numerical lowering and drawing distinct. Emit PostScript first and add native framebuffer and shader consumers through the same boundary.

This is an implementable design and job packet. No new compiler proof, rendered movie, GPU execution or physical-device acceptance is claimed by this planning result.

## Required Behrend extension

[Behrend triangles — required pre-graphics semantics](behrend-triangles.md) incorporates the user's subsequent requirement that Kai Behrend's *Introduction to Algebraic Stacks*, especially its stack-of-triangles treatment, shape the language itself.

This is not just another reference: retain families, explicit isomorphisms and automorphisms, pullbacks, compatible local descriptions and loop monodromy. Distinguish abstract shape from metric realization, so similarity cannot certify expansion. The addendum specifies contracts, positive/negative cases and amendments to the existing jobs; bind it into their next admitted inputs. It creates no separate project or job dispatch.

## Eight deliverables

1. [Requirements](requirements.md), extended by [Behrend semantics](behrend-triangles.md)
2. [Architecture and language decision](architecture.md)
3. [Core types and proof obligations](core-types.md)
4. [Examples and invalid cases](examples.md), extended by cases A–E in [Behrend semantics](behrend-triangles.md)
5. [Execution, interaction and export](execution.md)
6. [Reference study](references.md), with the Behrend primary source and reading map in the addendum
7. [Implementation plan](implementation-plan.md)
8. [Nine complete Sun jobs](jobs.md), subject to the addendum's explicit integration requirements

[Source state](source-state.tsv) binds the original repository observations. [Planning receipt](receipt.tsv) distinguishes that original source inspection and design from implementation evidence. The Behrend addendum records its own source and design-only status; the earlier receipt is not a new implementation or acceptance run for the addition.

The recovered original assignment proposed twelve boundaries and requested 8–12 Sun jobs. The nine jobs retain all twelve boundaries, combining objects with geometry, time with transformations, and the book example with its linked controls. The current request adds all ten animation references and explicit comparison with Idris 2, Agda and Rocq.

The original prompt was recovered through requirement summaries, not an authoritative verbatim transcript. This packet preserves the recovered requirements and the user's current corrections; it does not present itself as a copy of that original prompt.
