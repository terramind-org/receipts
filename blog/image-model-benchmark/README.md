# Image model benchmark, 25 October 2026

Data behind the terramind.com/blog post on image model speed and cost.

Eight image models from the Terramind Studio roster, every setting each one offers (64 configs), three prompts, one image per call: 192 calls, 189 succeeded. Muse Image refused every call from our account (HTTP 403) and has no numbers.

- `results/2026-10-25T05-41-52.json` — every call: model, settings, prompt, server inference time, wall time, price per image, credits, output size, and a per-config summary (medians over the three prompts).
- `results/2026-10-25T06-06-26-serial-recheck.json` — Grok Imagine and Recraft V4 re-run one call at a time, to rule out our own parallelism as the cause of their slow times.
- `index.html` — contact sheet of every image (open it from a local clone, or via GitHub Pages).
- `figures/` — the three comparison grids in the post.
- `images/thumbs/` — every image, 480 px.
- `images/full/` — the original files for the nine configs shown in the post; `images/web/` holds 1600 px copies.

Method:

- Speed is the provider's server-side inference time; queue wait is excluded. Wall time is from submit to result.
- Cost is the provider's published list price per image for that setting. The provider meters the token-billed models (GPT Image 2.5, Nano Banana 2.1, Nano Banana 2 Lite) by tokens; its published per-size table is used here, so a long prompt costs a little more than shown.
- Quality is not scored. The post reads the numbers against the Artificial Analysis image arena (Elo, as of 2026-10-25).
- n = 3 per config (one per prompt), one day. Treat small time differences as noise.

Prompts (set v1):

- `product` — Editorial product photograph of a cobalt blue hardcover notebook resting on a cream paper surface, cool diffused daylight from the left, soft shadow, sharp focus, slight medium-format grain, minimal composition. (4:3)
- `poster` — A minimalist event poster on cream paper. Large black headline reads exactly "FIELD NOTES". Below it, smaller text reads exactly "Volume 3 · November 14 · San Francisco". A single cobalt blue circle in the top right corner. Generous margins, Swiss grid layout. (3:4)
- `diagram` — A clean flat infographic explaining how a request flows: four labelled boxes left to right reading "Client", "API", "Queue", "Model", connected by arrows, with a small caption under each box. Ink on cream background, one cobalt accent on the "Model" box. (16:9)

GPT Image 2.5 takes an explicit size rather than an aspect ratio, so its images use the size in their config name.
