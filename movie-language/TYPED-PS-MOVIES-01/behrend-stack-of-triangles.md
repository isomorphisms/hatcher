# Behrend: the stack of triangles belongs before graphics

Required design addition, 2026-10-13, to TYPED-PS-MOVIES-01. The user explicitly requested incorporating the stack-of-triangles theory into the dependently typed pre-graphics language, not merely illustrating it or listing the paper.

Status: semantic requirements and planned acceptance cases, not implemented Idriç definitions. No proof-checker, PS, movie, GPU or physical-device execution is claimed. No job is dispatched and no merge or release is authorized by this addition. Implementation continues through Flexible Pipes, Kitchen and independent ai-ci acceptance.

## Primary source and scope

Kai Behrend, *Introduction to Algebraic Stacks*, author-hosted notes dated December 17, 2012: https://personal.math.ubc.ca/~behrend/math615A/stacksintro.pdf

Use §§1.1–1.3 for symmetry groupoids, continuous families, pullback, gluing and coarse versus fine classification; §§1.6–1.9 for equilateral triangles, orientation, stacks and versal families. Exercise 1.11, printed page 14, models families with a three-sheeted covering and continuous side lengths. Exercise 1.12, printed pages 14–15, gives overlap isomorphisms and the cocycle condition. The circle family on printed pages 13–14 admits local labels but no consistent global labelling.

These are initially topological-stack examples. Do not require scheme theory or all algebraic-stack machinery before implementing their useful semantic distinctions. The language contracts and acceptance design below are our proposed application of the source, not claims about software supplied by Behrend.

## The semantic boundary

Keep the following distinct:

- A triangle with a declared notion of equivalence.
- A specified isomorphism between two triangles, including its action on vertices and sides.
- A family of triangles over a parameter space, with continuity and local identification data.
- A chosen geometric depiction of a family member, including local labels, coordinate frame, scale and orientation choices.
- The path and painting operations emitted from that depiction.

A coordinate triple remains a useful representation of an embedded, labelled triangle. It must not define every possible meaning of triangle. A set of similarity classes, obtained by forgetting isomorphisms, is an explicitly information-losing coarse view, not a replacement for the family semantics.

Keep PostScript's operand stack separate from a mathematical stack. The two meanings of the word imply different contracts.

## 1. Explicit isomorphisms and automorphisms

Provide typed source and target objects for an isomorphism, executable transport on their constituent data, and checked identity, inverse and composition laws. Do not replace an isomorphism with a Boolean saying that two objects are equivalent. Do not identify every automorphism with the identity term.

Declare what maps are permitted. Unlabelled, unoriented triangles up to Euclidean similarity allow reflections; orientation-preserving triangles do not. Fully labelled triangles require the labels to be respected. A renderer's permission to apply an affine matrix does not make every affine map a similarity.

The first finite model can normalize side lengths to perimeter 2. Its parameter space is the positive triples summing to 2, with each side strictly smaller than 1. The group S₃ acts by permuting sides. Retain the resulting action groupoid: objects, arrows, composition and stabilizers. Its orbit space alone is insufficient. Continuous families will require the local gluing described below; implementing the pointwise groupoid does not by itself implement the stack.

Proof erasure may remove law witnesses that computation does not need. It must not erase the chosen permutation or other transport data when labels, selections or linked views depend on them.

## 2. Families and pullback, not only frame arrays

A family over B needs a fibre at each parameter, continuity evidence in a declared model, and local trivializations/transition maps where required. A dependent function from a set B to an object type does not automatically supply a continuous family.

For the initial unlabelled, unoriented side-length model, use Behrend's three-sheeted side covering over B, continuous positive lengths on that covering, and the perimeter/triangle conditions in every fibre. Do not require a global ordering of its sheets. A globally ordered coordinate description is a supported special case, not the universal representation.

Given a continuous parameter map f : A → B, pulling back a family over B produces one over A. Require identity/composition compatibility and transport of derived data. An ordinary movie restricts a family along an interval-valued path; a slider or time remapping is another base change. Record the additional order laws when a motion advertises expansion: pullback alone does not preserve monotonicity under an arbitrary time map.

A continuous deformation need not consist of isomorphisms between all of its fibres. A moving triangle may change similarity class or acquire additional symmetries. Keep continuous variation separate from isomorphism and from constant-stabilizer claims.

## 3. Coherent local gluing

For local families Fᵢ over an open cover Uᵢ of B, transition isomorphisms φᵢⱼ on overlaps must have the correct source and target and satisfy, on triple overlaps,

    φᵢₖ = φⱼₖ ∘ φᵢⱼ.

Include identity and inverse compatibility. Pairwise similarity, matching pictures or equal endpoint hashes do not supply these laws.

A checked cocycle is necessary, but a full stack claim additionally requires descent: compatible local families must glue, and local morphisms must glue uniquely in the appropriate sense. State the supported covers, constructions and proof boundary. Until that result exists, call the implementation a groupoid/family/gluing fragment rather than a proved implementation of stacks.

Labels and selections transport along actual identifications. Permit local labelling; require evidence for a global labelling or trivialization. An unmarked triangle with symmetry cannot acquire a canonical distinguished vertex merely because a sorting algorithm picks one.

## 4. Depiction must respect the chosen mathematical meaning

A representation must state which semantic object and local choices it realizes. A change of local presentation must transport points, sides, annotations and selections consistently. Identity and composition must hold for that transport.

Do not demand identical pixels for every isomorphic object: similar triangles may legitimately appear at different sizes or positions. Instead specify the corresponding geometric relation and the properties preserved. Absolute area is not an invariant of similarity; a selected vertex requires marking or explicit transport; orientation changes require the declared reflection policy.

Sorting side lengths may produce a coarse summary. It must not silently reset tracked labels or substitute for a continuous choice of representation, especially where sides become equal. Exact symmetry must not be inferred from nearly equal floating-point values.

## Required acceptance examples and failures

### A. Finite symmetries before drawing

Use perimeter-2 side triples:

    scalene       (1/2, 2/3, 5/6)
    isosceles     (3/5, 3/5, 4/5)
    equilateral   (2/3, 2/3, 2/3).

For the unlabelled, unoriented model, enumerate and verify stabilizer orders 1, 2 and 6. Require actual maps and their laws, not hard-coded counts. Three distinct copies of the isosceles object and one equilateral object should produce 24 arrows in their full symmetry groupoid. Restricting allowed maps to orientation-preserving ones must reject reflections; adding distinct vertex labels must change the allowed automorphisms accordingly.

Reject a model that collapses all six equilateral automorphisms into the identity, or permits arbitrary side permutations as self-isomorphisms of a scalene triangle.

### B. Equal shape data, different circle families

Construct two families with equilateral fibres over a circle. Describe them locally on an interval: glue the ends using the identity for one, and a three-cycle for the other. Their coarse shape maps agree, but their side coverings have different monodromy. Here monodromy means the permutation obtained by transporting sides once around the circle.

Prove that one circuit of the second family permutes a tracked side and that three circuits return it. Reject a claim that the same globally named side returns after one circuit. A movie may close as an unlabelled depiction while its marked version does not. A fixed global vertex array is therefore not a sufficient general family representation.

This finite gluing model does not require trigonometric coordinates. A later visualization can depict a 120-degree turn, but its angle evaluation and approximation need their own qualification.

### C. Bad gluing and lawful reparameterization

Provide a positive overlap fixture with composed transitions and a negative fixture whose transitions violate the cocycle. The latter must be rejected before PS emission. Check pullback identity/composition and retain side transport through a parameter remapping. Do not treat these finite checks as a proof of descent for arbitrary topological spaces.

## Integration into existing work

PS-MOV-01 owns the minimal object/isomorphism/action-groupoid contracts and the separation from embedded geometry. PS-MOV-02 owns continuous families, parameter pullback, explicit loop identification and transported markings. PS-MOV-04 must consume an explicit depiction without overwriting these semantics. PS-MOV-08 must keep linked selections consistent with the same transport. PS-MOV-09 independently rejects the symmetry, global-labelling and gluing failures above.

These extend the existing jobs; they do not create or dispatch another campaign. Establish the minimal contracts before freezing the triangle interface. Implement the finite examples first; qualify broader continuous families and effective descent as separately evidenced stages. Keep the reusable interface narrow and the stack mathematics in the appropriate library rather than embedding all of algebraic geometry into the Idriç compiler core.

## Evidence for this design addition

Read the existing Hatcher planning branch at a96dbfe879a6db0acf1f265b4b1979a68b622b1c and the relevant author-hosted source passages; visually inspected printed pages 8 and 14. A temporary exact-rational permutation calculation checked the three stabilizer counts, the 24-arrow count and the order of the three-cycle. That calculation is design arithmetic only, not a maintained implementation, an Idriç proof or an independent ai-ci acceptance receipt. Existing planning receipts apply only to the material they originally inspected; this addition does not inherit their checks.
