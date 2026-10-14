# Behrend triangle families: mandatory pre-graphics semantics

Requirement added 2026-10-13 for TYPED-PS-MOVIES-01, at the user's request. This is a design supplement, not an implemented stack library or a checked proof. It belongs above geometry, numerical lowering and PostScript emission, not merely in the illustration bibliography.

## Source and scope

The requested “stack of triangles” reference is Kai Behrend, *Introduction to Algebraic Stacks*.

- Author-hosted draft, dated 17 December 2012: <https://personal.math.ubc.ca/~behrend/math615A/stacksintro.pdf>.
- Published chapter in *Moduli Spaces* (2014): <https://www.cambridge.org/core/books/moduli-spaces/introduction-to-algebraic-stacks/AAAA0E5A01B9A50150C8A2552B73CF4F>.

All page numbers below refer to the 127-page author-hosted draft, not the differently paginated published chapter. Figures on printed pages 8, 13, 19 and 20 were inspected for this supplement. Do not imply that the whole paper has been inventoried. Link the paper; do not infer a redistribution licence.

Source locations for implementation: §1.1 (symmetry groupoids); §1.2, especially Exercises 1.11–1.12 (families, covers and gluing); §1.3 (pullback and the difference between coarse classification and families); §§1.4–1.7 (symmetry and orientation variants); §1.10 (degenerations); §§1.11 and 2.4 (change of presentation); §§2.1–2.3 (formal family and descent contracts).

The decisive source example is the pair of non-isomorphic families with the same coarse moduli map on printed pages 19–20. Our language must not identify families merely because each frame has the same similarity type.

## 1. A family is not a globally labelled coordinate array

Use Behrend's Exercise 1.11 as a concrete semantic target. Proposed notation, not compiler-tested Idriç:

```text
parameterSpace ← a topological space
sideCover      ← a three-sheeted covering of parameterSpace
sideLength     ← a continuous positive real function on sideCover

for each parameter:
    the three side lengths sum to 2
    each side length is less than the sum of the other two
```

The three sides over a parameter need not admit one continuous global ordering. Local enumerations and their transition permutations are data; sorting sides cannot replace them. Require continuity and covering evidence, not just a dependent function that supplies three numbers at every parameter.

The normalization describes similarity shape. Keep physical size, position, frame and a chosen geometric realization separate. Scaling an illustration can preserve its similarity class while changing its area; a constant shape-class caption cannot justify a claim that nothing expanded.

Start with explicit finite covers, permutations and restricted continuous constructions. Do not require an arbitrary topological-space decision procedure to deliver the first useful cases. Unsupported proof obligations remain explicit.

## 2. Preserve actual isomorphisms and automorphisms

Introduce an interface for objects and isomorphisms with typed source and target, identity, inverse, composition, and checked laws. An isomorphism contains the correspondence needed to transport points, sides, markings and derived constructions. It must not be erased into a Boolean or a bare assertion that two objects are equivalent.

Declare whether a triangle is labelled, unlabelled, oriented or unoriented, and which similarities are allowed. Keep the ordinary labelled coordinate triangle as a useful presentation; do not mistake it for the entire moduli problem.

A coarse shape identifier is explicitly information-losing. It is suitable for an overview plot, not for reconstructing arbitrary families or proving family equality. Distinct arrows with the same endpoints must remain distinct when they act differently on the depicted objects.

This contract can be expressed with explicit groupoid data and laws. It does not assert that an Idriç identity type already implements stack semantics, or make univalence a prerequisite. General stack theory remains a mathematical library behind narrow interfaces, not a new compiler primitive.

## 3. Interaction and motion use pullback

A construction must accept a parameter family, not just a single triangle. Given a continuous parameter map f : A → B and a family F over B, expose pullback f*F over A. A movie samples the pullback along its time path; a slider and a linked view use that same accepted family revision.

Check identity and composition of pullbacks, with explicit coherent isomorphisms where the chosen representations are not definitionally equal. Transport derived marks through those isomorphisms. A change of local enumeration cannot silently rename the selected side.

Base change alone does not establish monotone expansion. Retain the existing motion domain, continuity, endpoint and throughout-time contracts. Time remapping still needs its own order-preservation evidence when the advertised motion requires it.

## 4. Gluing and loop closure need witnesses

Local families over an open cover require transition isomorphisms on overlaps. With transition φᵢⱼ from the i presentation to the j presentation, the triple-overlap obligation is

```text
φⱼₖ ∘ φᵢⱼ = φᵢₖ
```

Include identity and inverse compatibility and a justified gluing operation. State its uniqueness relative to the specified gluing data, up to compatible isomorphism; do not assert that an object with symmetries has a unique automorphism.

A loop of unlabelled objects may close using an explicit endpoint isomorphism. That is distinct from a strict loop of a fully marked scene. The endpoint correspondence may permute sides or vertices: preserve this monodromy instead of replacing it with identity because the first and last pictures look alike.

Direct seeking must compute the same transported marking as playback from the declared start. Do not make the result depend on accidental mutable playback history.

## 5. Representation-independent meaning, not identical pixels

For every supported derived construction, require compatibility with the declared isomorphisms and parameter pullback. Drawing a transported object must represent the transported mathematical construction under the declared view relation. Different coordinate choices need not yield identical pixels.

A choice of a vertex, orientation or chart is additional data unless an invariant construction supplies it. In particular, a command that chooses one vertex of an unmarked equilateral triangle cannot claim invariance under all its symmetries. It must request a marking or expose a presentation-dependent choice. Camera-dependent placement of explanatory text is separate from selection of a mathematical vertex.

Changing an atlas or family presentation needs an appropriate equivalence witness, not an equality of arrays. General Morita-equivalence machinery may be staged later, but the interface must not rule out equivalent presentations with different indexing spaces.

Do not silently admit collinear or collapsed triangles by replacing strict inequalities with non-strict ones. Degenerate variants require their own declared objects, allowed maps and source-grounded semantics; no compactification is selected by this supplement.

## 6. Required acceptance cases

These are proposed tests, not executed results.

| Case | Required outcome |
| --- | --- |
| Unlabelled, unoriented nondegenerate triangles with all similarities allowed | Recover automorphism counts 1 for scalene, 2 for non-equilateral isosceles and 6 for equilateral; check actual actions, not only counts. |
| Locally enumerated side cover | Preserve transition permutations and reject an incompatible purported global labelling. |
| Nested parameter changes | Direct pullback and successive pullbacks agree through the specified coherent isomorphism; derived marks agree after transport. |
| Broken overlap data | Reject a deliberately false triple-overlap equation. |
| Equal coarse data, different families | Preserve the distinction in Behrend's printed-page-19–20 example; no family-isomorphism certificate from equality of shape summaries. |
| Loop with nontrivial endpoint correspondence | Report the induced permutation; reject a strict marked-scene loop claim when its marking does not return. |
| Symmetry-breaking selection | Reject an unqualified invariant “choose one vertex” operation on an unmarked equilateral triangle. |
| Similarity-normalized expansion | Keep shape invariants constant while correctly deriving physical length and area changes from the retained scale. |

An additional exact regression can use a fixed non-equilateral isosceles triangle over a circle: compare identity endpoint gluing with gluing that exchanges its equal sides. Their side covers have respectively three and two connected components, so the families cannot be isomorphic even though their coarse shape maps coincide. This is a proposed implementation fixture, not a claim of existing checked code.

## 7. Integration into existing work

Apply this supplement before accepting the shared pre-graphics interfaces:

- PS-MOV-01: object/isomorphism interfaces, family indexing, explicit presentation and marking data.
- PS-MOV-02: pullback-based motion, coherence, witnessed loop closure and transport.
- PS-MOV-03: compare readable notation without concealing these distinctions; a new parser remains conditional.
- PS-MOV-04/05: preserve construction provenance through PS and follower rendering; no quotient-by-appearance shortcut.
- PS-MOV-06/08: deterministic seeking, linked controls and local-chart transitions.
- PS-MOV-09: independent positive and deliberately broken family/symmetry/descent fixtures.

Keep the existing coordinate-triangle/disk/Venn delivery path. Add this semantic requirement without silently replacing the book-figure selection or starting a second animation implementation. The full stack library is not a prerequisite for the first coordinate-triangle render, but an interface that permanently discards correspondence and gluing data is not an acceptable foundation.

Any implementation work still requires Flexible Pipes admission and receipts, Kitchen execution where applicable, and independent ai-ci acceptance. This documentation update dispatches no job, claims no typecheck or rendering result, and grants no merge or release authority.
