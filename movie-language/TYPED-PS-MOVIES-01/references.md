# Reference study

## Scope and evidence

All ten repositories from the pasted animation list were recovered. Five recent forks were independently located and their heads read. The other five were inspected at upstream heads. This was a bounded source study of the paths below, not an audit or execution of every repository.

The “complete motion design stack” marketing description is not acceptance evidence. No claim about a particular model's actual use, star counts or a guaranteed 60 FPS follows from that post.

## Animation sources

| Reference and inspected revision | Source inspected | Transferable idea and logical condition |
| --- | --- | --- |
| [Manim](https://github.com/3b1b/manim/tree/fafa083a4fb274bba9cabde0b6e2f50ba6da0622) | manimlib/animation/transform.py | Aligns source/target object data and interpolates related objects. Borrow correspondence and explicit begin/end handling; array alignment does not prove incidence, nondegeneracy or isotopy. |
| [Playwright fork](https://github.com/isomorphisms/playwright/tree/a3401cfe0dcf317101572d025fa46248d0779b42) | packages/playwright-core/src/client/clock.ts | Controlled clock installation, pause and advancement suggest explicit capture clocks. They do not establish history-independent mathematical evaluation or deterministic raster bytes. |
| [Anime.js fork](https://github.com/isomorphisms/anime/tree/01b81be1df6843ccfe0a71c0699a746bf740dd77) | src/timeline/timeline.js; src/easings/eases/parser.js | Nested timings, labels and easing composition are useful. Back, Bounce and Elastic demonstrate why a generic easing cannot be assigned a monotonicity guarantee. |
| [PixiJS fork](https://github.com/isomorphisms/pixijs/tree/65552017d23255c1442a7d4ac7f0d49e3225fb1d) | src/scene/container/Container.ts | Explicit local/group/world transforms suggest frame-aware geometry and shared composition. Coordinate frames must be typed; a scene graph's hierarchy does not prove the depicted relationships. |
| [WhisperX](https://github.com/m-bain/whisperX/tree/771b4a14a9486f8fd5aef18ef49e35d639523dd3) | README.md; whisperx/alignment.py | Word alignment can support optional narration. Estimated timestamps, missing alignments and recognition errors stay separate from verified mathematical claims. |
| [Remotion fork](https://github.com/isomorphisms/remotion/tree/d807df0f3a8d3a7d6a65c06b4dfcc507ed077f49) | packages/core/src/use-current-frame.ts; interpolate.ts; Sequence.tsx | Explicit frame context, sequence offsets, playback rate and extrapolation policies inform movie semantics. Reuse those distinctions without introducing React or a browser into the native runtime. |
| [Theatre.js](https://github.com/theatre-js/theatre/tree/6ea82b938ea49609489f6377ded693ccc6ee8f5b) | packages/core/src/sequences/interpolationTripleAtPosition.ts | A reactive time-dependent interpolation result and explicit keyframe boundaries suggest linked derived views. The source permits different endpoint types; a mathematical transition needs a stricter compatibility proof. |
| [GreenSock fork](https://github.com/isomorphisms/greensock/tree/13e2b790546426a1a2e0e9b409f3f8dc6d6611f2) | src/gsap-core.js | Child/parent clocks, reversal, looping, easing and rounded timing expose useful composition questions. Reverse/yoyo and overshoot require explicit contract changes. |
| [Lottie](https://github.com/airbnb/lottie-web/tree/bede03d25d232826e0c9dca1733d542d8a7754fb) | player/js/utils/PropertyFactory.js | Serialized keyframes, hold behavior, local frame offsets and Bézier interpolation suggest a compact movie description. Imported tracks remain untrusted until validated against object and motion contracts. |
| [VideoDB](https://github.com/video-db/videodb-python/tree/9d6e55fb6115d6b210d7609105dd2601115b98ad) | videodb/timeline.py; videodb/editor.py; README.md | Separate clips, assets and timed overlays inform optional media composition. The legacy timeline module is explicitly deprecated and stream generation calls a service; neither becomes a first-slice dependency. |

Study mechanisms before borrowing implementation. Retain authorship/notices and evaluate each actual source's reuse terms before copying it. GreenSock's inspected header names its standard license and reserves rights; publicly readable source is not blanket permission. No upstream code is copied into this plan.

The existing FRAMEBUFFER-MOTION-01 work owns broad native translation of animation/rendering ideas. PS-MOV-05 owns the proof-bearing interchange and preservation boundary, avoiding a competing animation port.

## Idris 2, Agda and Rocq

| System | Concrete ideas | Limit that must remain explicit |
| --- | --- | --- |
| [Idris 2 equality and totality](https://idris2.readthedocs.io/en/latest/tutorial/theorems.html) and [multiplicities](https://idris2.readthedocs.io/en/latest/tutorial/multiplicities.html) | Dependent result types, explicit equality/transport and erased evidence alongside executable data | Totality is part of the proof contract. The published tutorial warns about checker limitations; the actual pinned checker needs its own qualification. |
| [Safe Agda](https://agda.readthedocs.io/en/stable/language/safe-agda.html) | A checked fragment excluding postulates, unsolved metas and disabled checks, including imported modules | Safe logical checking does not certify external rendering or arbitrary foreign compilation. |
| [Cubical Agda](https://agda.readthedocs.io/en/latest/language/cubical.html) | Paths, transport and quotient-oriented constructions inform object identity and topology | A cubical interval is not automatically an ordered real clock or a proof of Euclidean motion. |
| [Rocq extraction](https://rocq-prover.org/doc/V9.1.1/refman/addendum/extraction.html) | Separate computational witnesses from proofs; audit assumptions and prove a small decidable checker's soundness | Custom extraction mappings and foreign constants have unchecked responsibilities. A proof of existence or extracted program is not automatically a qualified Idriç/GPU implementation. |

Recommended use: Idriç is the implementation surface; Idris 2 is the inherited technical reference; Agda and Rocq challenge the small logical and preservation rules. Select one independent prover for the first cross-check according to qualified availability rather than requiring three parallel implementations.

## Drawing and book sources

[Casselman's author-hosted manual](https://personal.math.ubc.ca/~cass/graphics/manual/) covers named geometry, procedures, curves, transformations, perspective and 3D drawing. Its source programs show inspectable geometry and drawing state. Keep those as design material and source links; the author-hosted material's reproduction restrictions remain distinct from original Idriç work.

The current corpus is [dilapidated-shed/casselman](https://github.com/dilapidated-shed/casselman/tree/79b155f4a4f37826b49c7ecbeb494bda6add41d4), which records Casselman, MetaPost and other drawing-program provenance. The older isomorphisms/casselman address redirects.

[Hatcher's initial figure inventory](https://github.com/isomorphisms/hatcher/blob/b15c9d1af3e63ff71bf90d11903755ab9ceeb439/books/figures/README.md) is text-located and incomplete. [Francis's inventory](https://github.com/isomorphisms/hatcher/blob/a0fd71bccc05257afd2105dd3862abbdded8be27/books/figures/francis.md) is a contents-based inventory of numbered groups, with visual/panel verification still outstanding. Preserve those evidence levels.

## Existing implementation observations

- [CollegeVenn.idric](https://github.com/isomorphisms/flexible-pipes/blob/6549cc945577bc0565bd679588095672410c5407/models/CollegeVenn.idric) has dependent event/population/frame indices and bounded-fraction evidence. Its growth function is unproved. Its execution failure remains separate recovery work.
- [Kitchen movie-from-stills](https://github.com/isomorphisms/kitchen/blob/df14daf8cc612283ea210f206f0097a31db122a0/tasks/movie-from-stills/README.md) supplies the established stills-to-MP4 boundary.
- [rough.framebuffer](https://github.com/isomorphisms/rough.framebuffer/blob/3d897f35e015dbe6a914e4a571e3ac94073c1ac4/README.md) uses Field Mouse geometry and a C renderer over a caller-owned pixel buffer; its README names the current limited stroke/shape slice.
- [Shader backend](https://github.com/fuego-ironworks/idris-shader-backend/blob/4a29362e580df393e4d64a9929e4c1e592ac4c53/README.md) has a deliberately restricted checked-source-to-GLSL path. Its Idriç integration and actual renderer selection are separate boundaries.
- [Idriç geometry inventory](https://github.com/isomorphisms/Idric/issues/108) separates semantic carriers, quotient relations, orientation and representation loss.
- [FP delivery contract](https://github.com/isomorphisms/flexible-pipes/blob/def2a66fe61a2b23440f98031f1defa738a0d1ee/docs/job-delivery.md) distinguishes exact captured output, visible delivery and dispatch. Its documented ChatGPT sink limitation is not erased by this report.
- [ai-ci](https://github.com/isomorphisms/ai-ci/blob/3d174000649f9f828c29e6be981cfd0e60646014/README.md) already distinguishes media-decoding checks from mathematical semantic verification. Extend that boundary rather than calling changed pixels a proof.
