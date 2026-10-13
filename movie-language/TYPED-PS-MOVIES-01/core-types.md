# Core types and proof obligations

These are semantic contracts, not executable declarations. Implementation must use the current Idriç style and actual supported syntax.

## Inputs and constructions

| Concept | Meaning and required evidence |
| --- | --- |
| Accepted parameters | Input values together with evidence that they belong to the construction's domain |
| Construction identity | The object/construction referred to, independent of a renderer's mutable storage address |
| Checked construction | Named inputs, derived objects and the propositions advertised by the result |
| Point in a coordinate frame | Coordinates with dimension, units and frame identity |
| Segment between points | Endpoints that remain references to those points |
| Nondegenerate triangle | Three points with a nonzero signed doubled area |
| Unique line intersection | Intersection point plus nonparallel-line evidence and incidence in both lines |
| Region in a universe | Membership/subset meaning tied to one universe |
| Conditional fraction | Numerator derived from event ∩ population; denominator from population; positivity or explicit undefined state |

A phantom index or descriptive name is insufficient on its own. A constructor must require checked evidence, or the value must be created by a validated procedure whose success implies the stated proposition.

## Motion

A certified motion comprises a parameter domain, an initial object, evaluation at any admissible time, and evidence for its endpoint and throughout-time claims.

For the initial continuous language, use rational-coefficient formulas with a real-interval interpretation and proved rules. Actual frame samples use exact rational times. Proving a property only at sampled rational times is not a proof about all real times.

A monotone time remapping must map the allowed interval to itself, have the specified endpoints, and preserve order. Composing a certified expansion with such a remapping preserves nondecreasing expansion.

The polynomial easing e(t) = 3t² − 2t³ is a useful first case on [0,1]: it has endpoints 0 and 1, and derivative 6t(1−t) is nonnegative. The implementation must establish the lemma rather than store a Boolean assertion.

For sequential clips, check that the end state of the first equals the start state of the second. Continuity is a separate obligation from endpoint matching; differentiability and velocity matching are stronger optional obligations.

Parallel changes share time and state identity and require compatibility of their writes or a proved combined construction. Independent property tracks cannot compete for the same mathematical parameter without a declared composition.

A loop needs a checked join. A reverse operation changes order-sensitive contracts. A path morph needs a proof of the property it advertises; equal-length point arrays do not prove an isotopy.

## Geometry and topology

Distinguish a topological object from its chosen embedding, immersion, quotient presentation or projection.

A map on a quotient must respect the equivalence relation. A deformation retraction must satisfy its endpoint and fixed-subspace laws and continuity. A regular homotopy must preserve immersion; it need not preserve embeddedness. Projected crossings and spatial self-intersections require different evidence.

Agda's cubical paths suggest useful identity and transport mechanisms. They are not automatically ordered Euclidean time or continuous geometric animations. Supply the interpretation that connects a formal path to the claimed topological map.

## Numerical representation

Begin the triangle and fraction examples with exact arithmetic. Do not silently apply the source language's ordinary floating-point default to a proposition needing exact equality.

A numerical representation names its scalar format and an error bound. Coordinate conversion, curve approximation, projection and rasterization contribute separately.

Nonzero exact geometry can become indistinguishable after rounding. To preserve separation or orientation on screen, prove a sufficient margin relative to conversion and display error, or refuse that display claim. Higher precision or another view is an explicit choice.

An interval computation whose enclosure straddles a required boundary is inconclusive. It cannot return a proof because its midpoint appears favorable.

## Drawing state

A drawing interface tracks enough state to prohibit missing-current-point operations, mistaken open/closed-path use, unbalanced save/restore and frame/unit confusion.

Its operands are derived points and paths with provenance. Raw PostScript or arbitrary numerical overrides cannot enter the certified interface without an explicitly unchecked boundary that loses the relevant guarantee.

Saving graphics state does not save the mathematical construction. State rules for PostScript and rules for the depicted object remain separate.

## Interactive state

Raw touch or slider input becomes a proposed parameter update. Validate the proposal before committing a new construction revision. Every derived path, caption and linked view then consumes that accepted revision.

Reject an invalid drag with a reason and retain the last valid construction. If projection onto the admissible domain is offered, it must be visible and specify what parameter was changed; it cannot be an undocumented repair.

## Proof discipline

Require checked total definitions and reject unresolved holes and unjustified escape hatches in the certified fragment. Record imported assumptions and primitives.

Idris 2 documents dependent equality, totality requirements and erased arguments, but its published theorem tutorial also warns about totality-checker limitations. Treat totality settings as part of the trust boundary, not as an independent proof of checker soundness.

Agda's safe mode is a useful reference for rejecting unfinished proofs, postulates and disabled checks throughout imports. Rocq's proof checking and assumption reporting are useful references for auditing a development's actual logical basis.

Proof erasure removes unnecessary runtime evidence; it must retain the mathematical data that determines the figure. A propositional existence proof does not necessarily provide the executable coordinate or algorithm required by the renderer.
