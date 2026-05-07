---
'@eigenpal/docx-js-editor': patch
---

Consolidate body-scoped `data-pm-start` DOM lookups behind `findBodyPmSpans` / `findBodyEmptyRuns` / `findBodyPmAnchors` / `findBodyPmAnchor` helpers in `@eigenpal/docx-core/layout-bridge`. Removes the lingering risk that body-only operations (caret resolution, selection painting, scroll restore, image `NodeSelection` lookup, sidebar anchor positioning, visual-line navigation) accidentally match a header or footer run whose ProseMirror position collides with a body position. Same bug class as #391; this finishes the cleanup started in #406.
