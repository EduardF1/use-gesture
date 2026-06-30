---
'@use-gesture/core': patch
---

Guard drag pointer capture so an `InvalidPointerId` from `setPointerCapture` does not abort the gesture.
