# Requirements

## The intended result

Construct mathematical illustrations whose visible content follows from checked mathematical data and checked changes to that data. The language must explain what a drawing represents and why a motion is allowed.

The same construction drives static PostScript, a movie, a time slider and linked views. A label cannot silently use another state or another conditioning population. A renderer cannot silently replace a proved transformation with coordinate interpolation.

## Required semantic distinctions

| Boundary | Required distinction |
| --- | --- |
| Mathematical object | The object, its identity, relations and declared facts |
| Construction | Inputs, hypotheses, calculated objects and evidence for the result |
| Geometric representation | Coordinates, parametrizations, meshes and charts representing that object |
| Motion | A time-indexed construction and the laws claimed throughout its domain |
| View | Projection, camera, viewport, clipping and display units |
| Numerical lowering | Exact values, approximations, chosen width, error bounds and failure conditions |
| Drawing | Paths, fills, strokes, labels, ordering and raster coverage |
| Delivery | Numbered frames, encoded media and independent evidence about the actual output |

A matrix represents a transformation; it does not supply its mathematical meaning. A picture of two crossing curves does not establish intersection in three dimensions. A closed pixel outline does not establish an embedded surface.

## What “expand” guarantees

An expansion contract must name its object, measured property, time direction, domain and reference frame.

The first disk contract keeps the center fixed and requires positive radius and nondecreasing radius throughout the interval. It implies inclusion of the earlier filled disk in the later disk.

These other claims are distinct: area grows, every distance from a center grows, a region grows by inclusion, or apparent screen size grows. One does not automatically establish another. Shape expansion about a point needs appropriate geometric hypotheses; a nondecreasing scale alone does not prove inclusion for an arbitrary non-star-shaped region.

Pauses may satisfy nondecreasing expansion. Strict growth is a stronger contract. Reversing an expansion produces a contraction. Playing it backward does not retain a forward-expansion claim.

## A well-typed movie

A well-typed movie contains:

- validated inputs and a named admissible parameter domain;
- constructions and references with consistent object identities;
- evidence for every advertised invariant and every motion composition;
- explicit treatment of endpoints, joints, degeneracies and unsupported inputs;
- a view and numerical representation with stated bounds;
- drawing operations derived from that checked state;
- labels, captions and optional narration bound to the same semantic claims;
- a sampling schedule that preserves the declared time semantics.

A successful typecheck establishes only the propositions actually represented by its types, under its stated assumptions. It does not establish arbitrary geometric truth, correctness of Ghostscript or fidelity of a hardware renderer.

## Mandatory examples

Start with a movable nondegenerate triangle. Then cover the expanding disk, the corrected college/jobs Venn movie, a Casselman construction and a source-linked Hatcher/Francis construction.

Every example must ultimately provide a checked construction, a PostScript figure and a targeted invalid example that is rejected. Movie examples additionally require a checked movement and actual rendered and decoded frames.

The early Casselman progression is triangle → pentagon and diagonal intersections → bounded Bézier approximation of the graph of x⁴. A regular pentagon needs algebraic or certified trigonometric values; rounded coordinates are not evidence of exact regularity.

## Mandatory Behrend pre-graphics semantics

Kai Behrend's *Introduction to Algebraic Stacks*, especially its stack of triangles, must inform the language itself, not merely appear in a bibliography or rendered example. The [Behrend triangle-family supplement](behrend-triangle-families.md) is part of these requirements.

Before accepting the shared semantic interfaces, preserve parameter families, actual isomorphisms and automorphisms, local presentations, pullback and its coherence, and witnessed gluing. Coarse shape equality cannot certify family equality. Marked and unmarked loops require different closure conditions, and physical expansion must not disappear when shape is normalized up to similarity.

The supplement assigns these obligations and targeted invalid cases to the existing PS-MOV jobs. A full general stack implementation is not required before the first coordinate-triangle render; permanently erasing correspondence or gluing data from the language is not permitted.

## Mandatory deformation-aware transformations

User requirement, 2026-10-13: transformations should know whether they are travelling in a versal family. This extends the Behrend family contract above. It is a design requirement, not a claim of implemented deformation theory or checked versality.

### The deformation problem and evidence are part of the type

Retain the deformation problem: objects, admissible deformations, allowed equivalences, markings, ground field and category. Formal, algebraic, analytic, smooth and topological claims must not be silently interchanged. Versality is relative to this problem and a specified base point or germ; a claim over a larger locus requires evidence throughout that locus.

Proposed interfaces, not compiler-tested syntax:

```text
family          : Family over base for deformationProblem
versalAt        : VersalAt deformationProblem family basePoint
parameterPath   : AdmissibleMap timeDomain base
travellingFamily ← pullback parameterPath family
```

A versality certificate must carry its hypotheses and evidence provenance. Keep machine-checked proofs, cited mathematical theorems with explicit assumptions, and unresolved obligations distinct. Unknown versality is not non-versality, and an author-supplied Boolean cannot grant a verified capability.

Keep these claims separate:

- Versal: the appropriate compatible lifting property for the declared deformation problem.
- Miniversal: versal with the specified minimality condition; in the usual fixed-field tangent-space setting, no redundant first-order deformation directions.
- Universal: the applicable representing property, with its precise uniqueness or groupoid-equivalence statement. Retain automorphisms; do not substitute a coarse moduli space or infer universality from miniversality.

In the formal setting, the contract must address compatible lifts across the allowed small extensions of local Artinian rings, including the required isomorphism data. First-order tangent coverage alone is not a general proof of versality. A theorem reducing the check to tangent data must bring all its hypotheses with it.

### Travelling inside a versal family is not being versal

The motion retains both its ambient family and the parameter map. The actual time-indexed family must be identified with the pullback through a checked comparison, not merely produce similar-looking fibres.

Do not transfer an ambient versality certificate to an arbitrary path or parameter slice. A smooth one-parameter slice can miss deformation directions available in a two-parameter family. Reindexing preserves the pullback provenance, not every universal property. A certificate at the starting point also does not establish versality everywhere along the journey.

For successive parameter changes, retain the existing coherent comparison between pullback along a composite and successive pullbacks. Captions and linked views must distinguish “path in this versal family” from “this restricted family is versal.”

The family supplies fibres; it does not automatically supply a canonical correspondence between their individual points. Tracking a vertex or other feature requires its own section, covering lift, chosen trivialization or other justified transport. A dependent family is not automatically a type-theoretic path identifying all fibres as equivalent.

### Realization, strata and changing guarantees

A formal deformation certificate does not by itself provide an evaluable movie at ordinary nonzero real times. Require an effective/convergent geometric realization as appropriate, an explicit comparison to the formal model, and the existing numerical bounds before rendering such a claim.

Triviality, isotriviality, smoothness and equisingularity are separate refinements, not mutually exclusive alternatives to versality. When a construction uses a discriminant or stratification, retain the path's membership, avoidance or crossing evidence. Do not infer preserved topology or symmetry merely from versality. Unsupported or undecided events remain explicit; sampled frames cannot certify their absence.

### Required exact acceptance additions

These are proposed fixtures, not executed tests.

1. For the represented formal deformation problem with base k[[u,v]], accept the base change u ↦ t, v ↦ 0 as a family over k[[t]], but reject its claim to versality for the full two-direction problem. Its tangent map misses the v direction. Retain its provenance in the universal ambient family.
2. Use the inclusion of the dual-number base k[z]/(z²) into the formal line as a tangent-isomorphism counterexample. The deformation u ↦ ε over k[ε]/(ε³) restricts to z ↦ ε over k[ε]/(ε²), but cannot lift through k[z]/(z²), since ε² ≠ 0 in the larger ring. Reject a versality certificate based only on the tangent isomorphism.
3. Reject promotion from a certificate at one base point to a whole interval, from formal versality to real-time evaluation without a realization, or from a family path to canonical feature transport without supporting data.
4. Check a declared discriminant crossing in an exact supported example; reject an incompatible smooth-fibre or fixed-stratum claim. Preserve the original monotonicity, marking and loop checks independently.

PS-MOV-01 owns problem-indexed family properties and evidence status. PS-MOV-02 owns parameter paths, pullback comparisons, certificate scope and transport. PS-MOV-03 must expose the distinctions without forcing authors to restate the mathematics. PS-MOV-08 binds linked views and captions to them. PS-MOV-09 independently checks the positive and negative fixtures. Bind this requirement revision into those jobs' next admitted inputs; do not start a parallel campaign.

Mathematical references for this extension: Stacks Project, [smooth morphisms of deformation categories, Tag 06HG](https://stacks.math.columbia.edu/tag/06HG), [versal formal objects, Tag 06SX](https://stacks.math.columbia.edu/tag/06SX), [minimality and tangent spaces, Tag 06IL](https://stacks.math.columbia.edu/tag/06IL), and [versal rings and local scope, Tag 0DQT](https://stacks.math.columbia.edu/tag/0DQT). The contracts and exact counterexamples above are our design application; they are not attributed to Behrend as a programming-language proposal.

This amendment records requirements only. It dispatches no job, claims no proof typecheck or rendered output, and grants no merge or release authority. Existing Flexible Pipes admission, Kitchen execution and independent ai-ci acceptance remain required for implementation.

## Observable acceptance

- The expanding disk accepts a proved increasing trajectory and rejects a shrinking trajectory.
- Correct endpoints cannot conceal degeneration between them.
- Overshoot, bounce, reversal and loops cannot inherit an incompatible monotonicity guarantee.
- A camera change cannot be silently counted as object motion.
- Every linked view consumes one accepted state revision.
- The Venn complement is the whole universe outside good jobs, including people outside both sets.
- Both Venn fractions and their text derive from the event and conditioning population.
- Unsupported lowering fails rather than silently changing semantics or choosing another renderer.
- Numerical error and stroke decoration cannot silently erase distinctions the example claims to show.
- Direct seeking and forward playback give the same semantic state at the same time.
- Frame-rate changes alter sampling, not the mathematical trajectory.
- Independent checks inspect actual emitted geometry and decoded output, with targeted broken counterparts.

Logical consistency does not prohibit deliberate impossible figures. Such a figure must be represented as a drawing of incompatible spatial constraints, not as a certified realizable three-dimensional object.
