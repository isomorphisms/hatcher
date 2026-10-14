# Architecture and language decision

## Decision

Begin inside Idriç. Use project-owned construction and motion libraries and a small checked scene description. Do not start by building another general compiler, PostScript interpreter, animation engine or movie encoder.

The integration is an architectural choice, not a claim that the current Idriç compiler already supports every required exact number, proof or target. Each unsupported capability must be recorded and assigned to its current owner.

## Compare the alternatives

| Candidate | Strength | Cost or limitation | Decision |
| --- | --- | --- | --- |
| Idriç library and checked scene description | Reuses dependent checking, readable domain vocabulary and existing project boundaries | Requires qualified numeric/proof support and preservation at each lowering | First implementation |
| Separate dependently typed movie language | Could tightly control effects, syntax and trusted operations | Duplicates elaboration, equality, totality, modules, diagnostics and proof tooling | Defer until concrete examples demonstrate an unmet need |
| Typed PostScript stack language | Can describe operand effects and drawing-state transitions closely | Stack safety alone does not establish geometry or lawful movement | Use state indexing at the drawing boundary; reconsider surface syntax later |
| Conventional animation engine with attached mathematical assertions | Existing timing, scene and export machinery | Independent tweened coordinates can bypass the construction | Study its mechanisms; do not make it the semantic authority |

A later standalone surface may parse into the same checked description. It must neither introduce another meaning for a construction nor accept unvalidated annotations as proofs.

## Ownership

| Owner | Responsibility |
| --- | --- |
| Hatcher | Movie-language requirements, construction examples and the initial checked scene interface |
| Idriç | Language facilities and reusable type/proof interfaces; retain established geometry ownership |
| Casselman | Provenance and historical drawing-program references, with original material kept distinct |
| Flexible Pipes | Admission, execution/replay and exact job/output identity |
| Kitchen | Tested rendering/export recipes and canonical movie assembly |
| rough.framebuffer / Field Mouse | Existing native drawing, rough decoration and framebuffer consumers |
| idris-shader-backend | Supported shader lowering and evidence that a renderer consumes generated output |
| ai-ci | Independent reusable acceptance, diagnostic rejection and evidence boundaries |

Do not move rings, modules, chain complexes or every project's mathematical ontology into the Idriç core. A narrow typed interface may refer to an object owned elsewhere.

## Construction before depiction

A construction produces named mathematical objects and evidence. A representation maps those objects into drawable geometry under declared choices.

Dependent features, such as an intersection point or fraction caption, refer to the same construction. They are recomputed from its inputs rather than separately animated.

Keep mathematical incidence separate from style. A rough stroke may decorate a certified segment within a declared bound. It does not become the segment or supply an independent intersection witness.

## The preservation obligation

For every supported operation, establish a precise relation between:

1. evaluating the checked construction or motion at a time;
2. realizing that result as geometry;
3. lowering the geometry to the target drawing operations;
4. observing the drawn result within declared numerical and display bounds.

For exact operations, the middle relationship can be equality in a mathematical model. For approximate paths or pixels, it must name a distance/error relation and any margins needed to preserve the advertised property.

Separate two claims: a theorem about the ideal emitter's semantics, and evidence about the actual serializer, interpreter, rasterizer and encoded movie. A theorem about one does not silently certify the other.

## A limited trusted boundary

Inventory the checker/compiler revision, arithmetic implementation, imported axioms or proof artifacts, foreign interfaces, serializer, PostScript numeric behavior, rasterizer and media tools. A digest establishes identity; it does not establish semantic correctness.

Use external Agda or Rocq developments to challenge and validate small lemmas and checker soundness. A theorem in an external prover is not automatically an Idriç witness. A transfer must bind the actual statement, assumptions, representations and executable computation.

Prefer a small decidable certificate checker when an external solver supplies evidence. Its soundness theorem and its actual implementation must be connected. Unchecked text saying “proved” is not a certificate.

Do not promise a formally verified GPU, Ghostscript or FFmpeg stack. Initially qualify those boundaries through explicit approximation models, independent geometry checks and targeted rendering evidence.

## Syntax and scope

Compare three small notations on the same examples: readable Idriç domain expressions, a typed PostScript-like stack description, and a compact declaration syntax for constructions and motions.

Choose the smallest surface that preserves object identity, conditions and errors. The first useful implementation can work through a library API; parser work is conditional on a demonstrated need.

Descriptions in this packet are mathematical design notation, not compiler-tested Idriç syntax.
