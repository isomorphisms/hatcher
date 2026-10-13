# Behrend triangles — required pre-graphics semantics

Requirement added 2026-10-13 to TYPED-PS-MOVIES-01 at the user's request. This is a semantic extension of the existing design, not a separate language or animation project. It must affect contracts and acceptance, not merely the bibliography.

Status: design requirements and mathematical examples. No new Idriç typechecking, implementation, rendered movie, or independent acceptance is claimed. Existing FP admission and ai-ci acceptance requirements remain in force; this addendum dispatches no job and authorizes no merge or release.

## Primary source

Kai Behrend, *Introduction to Algebraic Stacks*, lecture notes dated December 17, 2012:
https://www.math.ubc.ca/~behrend/math615A/stacksintro.pdf

Relevant reading: §1.1, families and symmetry groupoids, pp. 8–12; §1.2, continuous families and gluing, pp. 12–15, especially Exercises 1.11–1.12; §1.3, pullbacks and classification, pp. 15–22; §1.6, equilateral families, p. 25; §1.7, oriented triangles, pp. 25–31. Sections 1.8–1.9 and 2.1–2.4 supply the later stack formalism.

Behrend retains isomorphisms and symmetries while studying families. In his first triangle model, a three-sheeted cover of the parameter space carries positive side lengths satisfying strict triangle inequalities and perimeter 2. His equilateral example closes an interval family with a 120-degree twist: the coarse shape stays fixed, but the vertex cover is nontrivial. These are source facts; the language obligations below are our proposed application.

## Contracts before drawing

Use narrow project-owned interfaces, not an algebraic-stack engine inside the Idriç compiler. Names below describe contracts, not compiler-tested syntax.

| Contract | Required meaning |
| --- | --- |
| Triangle shape | The declared similarity problem, with labelled/unlabelled and oriented/unoriented variants explicit |
| Isomorphism from source to target | The actual invertible correspondence and its preservation evidence; composition accepts matching endpoints and satisfies identity, inverse and associativity laws |
| Family over a parameter space | Local continuous constructions with compatible identifications; not only a function returning a sorted side triple |
| Reindexing a family | Pullback along a declared continuous parameter map, with identity/composition coherence |
| Compatible local descriptions | Isomorphisms on overlaps, inverses, and equality of the two composites on triple overlaps; an effective gluing construction for the supported class |
| Metric realization | Actual size, units, placement and coordinate frame, linked to the abstract object |
| Display realization | Paths, labels, camera and approximation bounds derived from that metric realization |

Do not identify different automorphisms merely because they have the same source and target. The correspondence may control labels and subsequent constructions, so it is mathematical data, not an expendable assertion that some isomorphism exists.

A dependent index alone does not establish continuity or descent. Declare the parameter spaces and covers supported by the first library, prove the relevant laws there, and leave unsupported generality explicit. A bare groupoid or three coordinates do not amount to an implementation of a stack.

## Identity, symmetry and labels

For the initial unlabelled, unoriented model, retain all length-preserving side permutations. Use exact fixtures of perimeter 2:

- Scalene: (1/2, 2/3, 5/6), with one automorphism.
- Isosceles but not equilateral: (3/5, 3/5, 4/5), with two.
- Equilateral: (2/3, 2/3, 2/3), with six.

These counts include the identity. An oriented model excludes reflections; the corresponding counts are 1, 1 and 3. A fully vertex-labelled triangle has only the label-preserving identity. These are different contracts, not switches in drawing style.

For our interface, sorting sides may compute a coarse shape coordinate; it must not silently choose persistent identities for vertices or erase the family. A displayed label must refer to a specified local or global labelling. Changing a local presentation must carry that reference through its actual correspondence, rather than attaching it to whichever array slot is convenient.

## A movie is a family plus additional laws

Evaluate a family over an interval, or pull it back along a continuous parameter path. Add the existing endpoint and throughout-time proofs. A slider change is a change of parameter; a time remapping is a pullback with extra order conditions when it must preserve expansion.

Do not infer that different times are joined by similarity isomorphisms: a triangle can genuinely change shape. Distinguish movement through a family from an isomorphism between two descriptions. Continuity also does not supply an arbitrary canonical identification of every feature; require the relevant covering lift, chosen correspondence or other explicit construction.

Keep two loop contracts separate:

1. An abstract family loop carries a specified endpoint isomorphism, potentially with nontrivial monodromy.
2. A displayed loop additionally checks the realized seam, including metric size, placement, camera, decorations and any labels promised to return.

Amend the original exact-state join rule only at the abstract layer: a checked isomorphism can glue abstract family endpoints. It cannot waive the obligations for the actual movie seam.

## Shape equivalence does not prove expansion

Similarity forgets size. The original triangle at (0,0), (4,0), (1,3), scaled about its centroid by 1+t for 0 ≤ t ≤ 1, has constant normalized shape and increasing area 6(1+t)². The scale 1−t/2 has the same normalized shape but shrinks. Our expansion checker must accept the former only with its growth proof and reject the latter.

Put the expansion law on realized regions in one fixed ambient frame: earlier ≤ later implies earlier region ⊆ later region. For this convex triangle, a fixed centre inside it and a positive nondecreasing scale establish nesting. Isomorphism in the similarity groupoid cannot supply that evidence.

Changes of abstract presentation and camera coordinates must not covertly change the measured object. Do not infer on-screen growth from a shape-stack path. Retain the existing numerical, clipping and rasterization obligations.

## Required acceptance additions

Extend the current cases rather than replacing the initial checked triangle.

A. Enumerate the exact automorphisms above; reject a reflection in the oriented contract and a permutation that violates labels. Recompute symmetry at exact special parameter values rather than guessing from rounded pixels.

B. Compare two equilateral families over a circle: identity gluing versus a three-cycle at the seam. Both have constant coarse shape. Preserve the difference between their three disjoint vertex sheets and connected three-sheeted vertex cover. Reject a purported globally returning vertex label for the three-cycle unless the construction explicitly passes to a suitable cover. A drawing without labels may close when a vertex-labelled drawing does not.

C. Check an overlap diagram with compatible transitions; reject a triple-overlap mutation whose two composite correspondences differ. Equal-looking triangles are not evidence of a valid cocycle.

D. Test reindexing twice against the composite pullback. Preserve the family data and labels under a valid change of local description; do not require identical pixels from different coordinate presentations.

E. Run the expanding and shrinking realizations with identical normalized shape data. Reject any checker that certifies both merely because their shapes are similar. Keep strict triangle inequalities; degenerations require a separately declared extended object type, not silent repair.

## Integration into the existing jobs

PS-MOV-01 owns source/target-indexed isomorphisms, retained automorphisms, label choices and the distinction between shape and realization. PS-MOV-02 owns interval families, pullbacks, abstract joins, loop monodromy and the separate metric growth law. PS-MOV-03 must preserve these distinctions in the authoring interface. PS-MOV-04 and PS-MOV-06 must preserve the declared correspondences through drawing and seeking/export. PS-MOV-08 must keep linked views on the same family and accepted parameter. PS-MOV-09 owns independent positive/negative cases A–E.

These requirements constrain those jobs even if their original standalone text predates this addendum; bind this document into their next admitted inputs. Retain the existing first-triangle milestone. Full general descent, arbitrary moduli spaces and algebraic compactifications are not prerequisites for that milestone, but unsupported capabilities must not be represented as already checked.
