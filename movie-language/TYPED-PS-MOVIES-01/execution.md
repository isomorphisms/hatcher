# Execution, interaction and export

## Pure semantic evaluation

A movie evaluates its checked construction at a semantic time. It must not depend on previous frames, wall-clock delays, callback order or accumulation of small coordinate changes.

The reference result is the checked state and derived drawing geometry. Evaluate that state first; optimize caches, interpolation tables and GPU packets only when they preserve it.

Seek directly to times in scrambled order, repeat the same time and compare the result with forward playback. Fixed input revisions and seeds must give the same semantic output.

## Time and sampling

Keep seconds, normalized clip time, frame ordinal and encoded presentation time distinct.

Declare clip duration and endpoint policy. One useful inclusive schedule has N ≥ 2 frames at frame rate F, sample times k÷F for 0 ≤ k < N, and movement duration (N−1)÷F. The last endpoint is then held for one frame interval; the encoded duration is N÷F. Do not conflate these durations.

For a fixed movement duration, choose compatible schedules at different frame rates and compare at shared semantic times. Another policy may omit the endpoint sample, but it must declare that choice and validate the exported timing accordingly.

Clip composition must specify whether a shared endpoint is duplicated, held or sampled once. Monotonicity guarantees concern semantic forward time, not arbitrary slider scrubbing.

## Rendering

Use the checked scene description to derive paths, fills and semantic labels. Retain per-object construction/state identity in a trace or sidecar for diagnosis.

PostScript is the first serialization target. It is not itself the interactive runtime. Render PS through a pinned interpreter into contiguous, zero-based stills with declared viewport, resolution and settings.

Native framebuffer and GPU consumers receive the same accepted construction/geometry. Match their mathematical output and approximation contract, not arbitrary byte equality between antialiasing implementations.

A subpixel coverage rule must name sample positions, coverage composition and ownership of a boundary pixel. Roughness uses reproducible seeds and a bounded decoration envelope. Neither mechanism may silently change the certified incidence or semantic region.

Shader lowering must preserve chosen widths and defined operations. The inspected backend can lower both branches into temporaries before a final conditional, so a dead branch cannot be assumed to protect division by zero or an invalid index.

## Interaction

A proposed update is validated against the current construction domain. Commit a new revision only after validation. Publish that revision atomically to every linked view, caption and renderer packet.

Caches are keyed by accepted inputs, semantic time, view and representation settings. A cache hit must not mix geometry from one revision with text from another.

For a free drag, the result is either a valid updated construction or an explained rejection. Constraining/projecting a drag is a separately visible behavior.

## Movie assembly

The mathematical producer owns the trajectory, view and stills. Kitchen owns the established movie-from-stills assembly task. Preserve its input stills and explicit input frame rate.

Re-use the current stable Kitchen build entrypoint. If timing, audio or encoding requirements exceed it, qualify a change in Kitchen rather than inventing a project-local encoder.

Inspect the finished MP4: full decoding, actual frame count, dimensions, frame rate, timestamp policy, duration, final hold and audio rule. Container bytes need not be identical across unrelated codec builds.

## Narration and captions

Canonical claim text derives from the same semantic objects as on-screen labels. Bind captions and narration input to that text and its source revision.

WhisperX timestamps are observed or estimated alignment data. They can assist synchronization, but they cannot prove that a spoken mathematical statement is true or that recognition reproduced every word. Keep alignment confidence and unavailable timestamps explicit.

Keep narration optional for the first proof-bearing examples. It must not become a prerequisite for checking geometry.

## Execution and evidence

Flexible Pipes owns model/deterministic stage identity, admission and replay. Follow-on jobs must use its established stage/handoff interface; this plan introduces no parallel job registry or dispatcher.

ai-ci independently checks semantic and rendered consequences. A producer's receipt is evidence to inspect, not its own final verdict.

The current FP job-delivery documentation says a deployed ChatGPT visible-sink adapter is absent. This plan cannot assert real FP delivery/admission acceptance from local text or repository publication alone.

MIRO A1 remains the primary physical runtime target when mobile delivery is activated. MIRO C67 and TAB_P10 are separate targets with separate acceptance. All compilation and packaging happen off-device; publication, installation, behavior and GPU evidence remain distinct stages.

## Performance qualification

When a mobile consumer is activated, declare its measured workload and performance budget before judging the candidate. Record input-to-accepted-state delay, state-to-render delay, frame-time distribution and dropped/stale revisions on that exact device. Compare cold and steady operation with the same source/artifact identity.

A claimed 60 FPS from an upstream post is not the performance requirement. Establish the budget from the maintained device and example, and retain responsiveness evidence separately from mathematical correctness.
