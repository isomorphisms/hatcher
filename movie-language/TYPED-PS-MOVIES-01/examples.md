# Examples and targeted failures

All examples below are planned acceptance cases. No new checked source or rendered figure is claimed here.

## 1. Triangle first

Use corners (0,0), (4,0), and (1,3). Its signed doubled area is 12.

The movable-vertex version places the third corner at (1+2t, 3+t), with 0 ≤ t ≤ 1. Its signed doubled area is 4(3+t), which stays between 12 and 16. This supplies a concrete proof target for nondegeneracy throughout motion.

An expansion variant scales the original triangle about its centroid (5÷3,1) by 1+t. Its area changes from 6 to 24 and its signed doubled area becomes 12(1+t)². Triangle convexity and a center in the triangle supply the hypotheses for nested filled regions.

Derive edges, vertex marks, area caption and any linked coordinate view from those same corners.

Reject collinear corners, a zero scale and a claimed expansion using 1−t÷2.

A separate adversarial example rotates the endpoint triangle by 180° about its center and then linearly interpolates corresponding endpoint coordinates. Both endpoint triangles have positive area, but halfway every corner collapses to the center. Valid endpoint pictures do not prove a valid trajectory.

Required output: checked construction and motion, static PS, numbered frames, and failures with diagnostics for degeneracy and incompatible motion.

## 2. Expanding disk

Keep the center fixed. Set radius r(t) = 1+t on [0,1]. The radius stays positive and does not decrease; hence earlier filled disks are contained in later ones.

Use either linear time or the proved easing 3t²−2t³. A shrinking radius, an easing that decreases, or an incompatible reverse/loop must lose or fail the expansion contract.

Start with a fixed affine view and declared clipping bounds. A camera zoom can make an expanding world object appear smaller; the first example must not silently allow that. Actual raster coverage can fluctuate at boundary pixels, so do not equate strict world growth with strictly increasing pixel counts.

Required output: PS snapshots at specified times, the whole movie, analytic motion evidence and a targeted rejected shrinking program.

## 3. College and good jobs

Use one universe, the college set and the good-job set. The four disjoint cells are both, college only, good job only, and neither.

“Bad job or no job” is universe minus good jobs. It includes both college-only and neither. It is not another independently authored circle.

The two questions are:

- good jobs among college graduates: measure(good jobs ∩ college) ÷ measure(college);
- college graduates among people with a good job: measure(college ∩ good jobs) ÷ measure(good jobs).

Use cell weights 2,3,5,7 as an asymmetric fixture. The answers are 2÷5 = 40% and 2÷7 ≈ 28.57%. Equal answers in a symmetric fixture must not erase the distinction between questions. An empty conditioning population gives “undefined,” not 0%.

The inspected CollegeVenn source derives events, conditioning populations, fractions and labels, and includes 768 region-query oracle cases. Its growth function has no monotonicity witness. No new execution of those cases was performed in this plan.

Its movie weights are 500, college_growth, 820 and 7280−college_growth, totaling 8600. The first fraction falls from 50% to 20%; the second remains 500÷1320 ≈ 37.9%. These are illustrative weights, not employment statistics.

Keep labels and any proportional areas tied to the same measure. A schematic Venn diagram must say that its geometry is schematic. Claiming proportional area requires a layout with a verified area relation and error bound; counts alone do not prove it. Two circles cannot realize every prescribed four-cell area layout.

Continue the existing Venn recovery work. This language plan does not authorize a competing renderer or erase its compiler/runtime failure records.

## 4. Casselman pentagon and intersections

Construct the outer pentagon, diagonals and inner vertices by intersection. Do not hand-enter inner corners.

Prove required intersections exist and are unique, and retain incidence while parameters move. Reject parallel or coincident lines, zero denominators and a motion crossing a forbidden degeneracy.

A claim of regularity requires exact algebraic constructions or separately certified approximations. Arbitrary rational pentagon coordinates may provide a convex-pentagon example but not an exact regular pentagon.

Retain source provenance without redistributing restricted original programs.

## 5. Graph of x⁴ and cubic Bézier approximation

For cubic Hermite interpolation H on [a,b], matching x⁴ and its derivative at both ends gives the exact error

    x⁴ − H(x) = (x−a)²(x−b)².

Writing h = b−a, the maximum vertical error is h⁴÷16. With interval length 1 the bound is 1÷16; splitting into two length-½ intervals reduces each bound to 1÷256.

Reject a tolerance of 1÷100 for the unsplit interval; subdivision may then qualify it. Convert a mathematical error bound into a screen-space bound using the actual view.

An error bound alone does not preserve every shape claim. On [0,1], H(x)=2x³−x² becomes negative near zero although x⁴ is nonnegative. Do not claim exact positivity merely because the approximation has a small error. A positivity-preserving representation needs an additional argument or an explicitly approximate display contract.

## 6. Hatcher source-linked construction

Use the inventory entry TN-001: rational points on the unit circle constructed by secants through (0,1), printed page 2 of the September 2024 Topology of Numbers revision.

Let the moving point on the horizontal axis be (axis_position,0). The other circle intersection is

    (2 × axis_position ÷ (1+axis_position²), (axis_position²−1) ÷ (1+axis_position²)).

The denominator is positive for every rational axis_position. Squaring and adding the coordinates gives 1. The point, secant, coordinate caption and circle view must follow from the same axis_position. A mutated coordinate formula must fail the circle-membership claim.

This is a source-linked implementation choice, not a claim that the book's visual page was inspected. The current inventory is text-located; the primary PDF retrieval timed out in this planning run. Confirm the precise page/figure against the named edition before claiming reproduction.

Francis's saddle and projection entries provide later candidates. Its inventory identifies 87 numbered figure groups and four plates, not a visually verified count of individual panels. Do not choose an eversion or Möbius animation merely because it is a familiar demo.

## 7. A deliberate impossible figure

Francis's impossible-tribar entries suggest a useful negative example. A consistent two-dimensional drawing of an illusion can coexist with a proof that its proposed global depth constraints cannot describe the claimed rigid three-dimensional object.

The drawing is admissible as an illustration of inconsistency. A constructor claiming a realizable spatial object must reject the contradictory depth constraints.
