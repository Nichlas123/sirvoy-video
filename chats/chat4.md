# Video export options

_Started 2026-05-03 07:12 UTC_

---

## User

Can you remove the "download mp4" and "Transparent WebM" so that we don't confuse claude code

## Assistant

I'll find and remove those download buttons.

_[tool: grep]_

Let me read the relevant section to remove the buttons cleanly.

_[tool: read_file]_

I'll remove both the floating export buttons and the corresponding controls in the Tweaks panel.

_[tool: str_replace_edit]_

_[tool: done]_

That Babel "deoptimised styling" warning is just a perf note about the inline script size (the embedded base64 room images), not a real error — it was there before this edit. Removed both the floating "Download MP4" / "Transparent WebM" buttons and their counterparts inside the Tweaks panel. The export functions are still in the file, just not wired to any UI — let me know if you'd like those code blocks stripped out too.

## User

is the black space here transparent background?

## Assistant

_[tool: read_file]_

Yes — that dark checkerboard pattern you're seeing is the transparent background. The body has `background: transparent` set on `html, body`, and then a checkerboard pattern is drawn on top deliberately so you can visually tell where the transparency is during preview. The Stage canvas itself is transparent (the "bgMode" tweak defaults to `'none'`), so when exported, only the rounded video content has pixels — everything around it is true alpha.

If you want to confirm: in the Tweaks panel, "Export background" lets you swap between `green / cream / navy / none`. `none` = transparent (checkerboard shows through); the others fill the canvas with a solid color.

