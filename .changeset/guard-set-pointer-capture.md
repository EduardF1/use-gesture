---
'@use-gesture/core': patch
---

fix(drag): wrap `setPointerCapture` in try/catch to swallow the `InvalidPointerId` DOMException thrown when the pointer id is no longer valid by the time the drag engine calls it (e.g. the pointer was released between event dispatch and the capture call during rapid touch interactions or certain browser quirks). The drag now proceeds without pointer capture instead of aborting, mirroring the already-guarded `releasePointerCapture` call in `pointerUp`.
