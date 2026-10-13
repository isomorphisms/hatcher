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
