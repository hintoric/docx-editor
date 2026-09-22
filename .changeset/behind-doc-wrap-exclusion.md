---
'@docx-editor.dev/core': patch
---

Wrap text around floating drawings that set `behindDoc` together with a real wrap type. `behindDoc` chooses the paint layer and only selects behind/in-front for `wrapNone`, which the projection already resolves, but the layout re-tested the flag and dropped the exclusion zone — so a `wrapSquare` or `wrapTight` float marked `behindDoc="true"` had text running straight through it instead of around it. Such floats now displace text exactly as in-front ones do and are still painted under the glyphs; `wrapNone` watermarks are unaffected.
