# Beyond the Screen — published Preview verification

Source commit: `817d41baafea2f754f6165b5cb0aa270ca8842f1`. The publicly hosted static build was exercised on 6 November 2026 in Chromium headless with SwiftShader. The render loop deliberately caps software rendering to roughly 30 FPS and sets its pixel ratio to 0.75, so the illustration is visibly softer than on a full-resolution GPU. The following are browser requestAnimationFrame callback intervals across a scripted session including idle periods, not measured displayed frames, GPU timing, or proof of 60 FPS.

| Browser emulation | p50 | p95 | intervals over 33.34ms | Long tasks |
| --- | ---: | ---: | ---: | ---: |
| Mobile 390×844 | 16.7ms | 16.8ms | 6 / 889 | 2, max 88ms |
| Desktop 1280×900 | 16.7ms | 16.8ms | 8 / 992 | 1, max 132ms |
| Mobile, CPU ×4 | 16.7ms | 16.8ms | 12 / 865 | 8, max 357ms |
| Reduced Motion 320×640 | 16.7ms | 16.8ms | 3 / 516 | 1, max 113ms |

The scripted sessions checked forward/reverse pull, rollback, opening, editing a long Thai message, 3 replays, automated axe checks, viewport overflow and JavaScript page errors. No axe violations or page errors were recorded. Mobile and desktop video sessions also had no HTTP errors. A separate local WebGL context-loss test loaded the old postcard and preserved the edited name. These do not substitute for accessibility review, a physical-device test, performance tracing of the GPU, or an independent blind user study.

The video labelled opening covers the current prototype, not the complete requested three-part experience. The visual opening still resembles entering a depth-displaced illustration and does not meet the owner's quality gate. The texture on the postcard is still one surface; the original duplicate folding lighthouse image is gone, but the visual transformation is not yet the requested fully 3D fantasy world. The lighthouse beam search and universe finale are not implemented.
