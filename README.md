# 3DVision2026

Interactive concept demos for the **3D Vision – NeRFs & INR** course. Move the sliders, predict what happens, then reveal the answer.

## Live links

| Page | Address | What it is |
|---|---|---|
| Course home | <https://znjubery.github.io/3DVision2026/> | Landing page listing every module |
| Module 4 concepts | <https://znjubery.github.io/3DVision2026/module4/> | 30 interactive concepts from Lectures 4.1, 4.2 and 4.3 |

The links work once GitHub Pages is turned on (see [Publishing](#publishing)).

## Module 4 · direct link to each concept

Add `#c` and the concept number to the Module 4 address to open that concept directly, e.g. `module4/#c14`.


### Lecture 4.1 · Realism: lighting, materials and relighting

| # | Concept | Slide | In one line |
|---|---|---|---|
| 1 | [Same shape, different material](https://znjubery.github.io/3DVision2026/module4/#c1) | slides 3–4 | Geometry gives the outline. The material numbers give the look. |
| 2 | [Lambert: matte reflection](https://znjubery.github.io/3DVision2026/module4/#c2) | slide 5 | Matte brightness = albedo × cos(angle to the light), and it looks the same from every camera. |
| 3 | [Phong: the moving highlight](https://znjubery.github.io/3DVision2026/module4/#c3) | slide 5 | Highlight = ks·cosˢ(angle from mirror). Bigger s, tighter spot. |
| 4 | [Cook-Torrance: microfacets and Fresnel](https://znjubery.github.io/3DVision2026/module4/#c4) | slide 5 | Roughness sets the width, F₀ sets the strength, and everything glares at grazing angles. |
| 5 | [Learning reflectance from views](https://znjubery.github.io/3DVision2026/module4/#c5) | slides 6 and 8 | A learned material is only as good as the view directions it was shown. |
| 6 | [Taking a photo apart: albedo × shading](https://znjubery.github.io/3DVision2026/module4/#c6) | slide 6 | One photo has two unknowns per pixel, so the split always needs an extra assumption or more photos. |
| 7 | [Normals from several lights: photometric stereo](https://znjubery.github.io/3DVision2026/module4/#c7) | slide 6 | Spread-out lights work like a wide stereo baseline: they make the equations well conditioned. |
| 8 | [Visibility: who sees the sun and the sky](https://znjubery.github.io/3DVision2026/module4/#c8) | slide 6 | The sun gives on/off shadows; the sky gives a smooth fraction. |
| 9 | [Lighting in a few numbers](https://znjubery.github.io/3DVision2026/module4/#c9) | slide 6 | Matte shading is a blurred sky, so about 5 numbers (2D) or 9 (3D) describe it. |
| 10 | [Relighting: same scene, new sun](https://znjubery.github.io/3DVision2026/module4/#c10) | slide 7 | Relit image = albedo × shading for the new light. A plain NeRF cannot do this. |
| 11 | [Material editing](https://znjubery.github.io/3DVision2026/module4/#c11) | slide 7 | Change one factor and re-multiply: new material, same light, same shape. |
| 12 | [Why relight field scans: sun by the hour](https://znjubery.github.io/3DVision2026/module4/#c12) | slide 9 | Compare field scans at the same light, or relight them first. |

### Lecture 4.2 · Efficiency and compression

| # | Concept | Slide | In one line |
|---|---|---|---|
| 13 | [The bottleneck: time per frame](https://znjubery.github.io/3DVision2026/module4/#c13) | slide 4 | Speed is set by how many times you ask a network per pixel. |
| 14 | [The bottleneck: memory](https://znjubery.github.io/3DVision2026/module4/#c14) | slide 4 | NeRF is small and slow; splats are big and fast. |
| 15 | [Multi-resolution hash encoding](https://znjubery.github.io/3DVision2026/module4/#c15) | slide 5 | Many resolutions in a small table: fast lookups replace most of the big network. |
| 16 | [Pruning and quantization](https://znjubery.github.io/3DVision2026/module4/#c16) | slide 6 | 8 bits is nearly free; below about 4 bits quality falls off a cliff. |
| 17 | [Knowledge distillation](https://znjubery.github.io/3DVision2026/module4/#c17) | slide 6 | A small model learns best from a big model's dense, clean answers. |
| 18 | [Splatting: stop when the pixel is full](https://znjubery.github.io/3DVision2026/module4/#c18) | slide 7 | No network, and most splats are never touched: that is why splatting is real time. |
| 19 | [View-dependent color costs numbers](https://znjubery.github.io/3DVision2026/module4/#c19) | slide 7 | Low orders blur highlights; high orders cost memory. Degree 3 is 48 of a splat's 59 numbers. |
| 20 | [MobileNeRF: triangles, then a tiny network](https://znjubery.github.io/3DVision2026/module4/#c20) | slide 8 | Rasterize first, then one small network call per pixel instead of dozens per ray. |
| 21 | [Size against quality: the frontier](https://znjubery.github.io/3DVision2026/module4/#c21) | slides 9 and 11 | Pick from the frontier; any setting below it wastes bytes or quality. |
| 22 | [How do we score a render? PSNR and SSIM](https://znjubery.github.io/3DVision2026/module4/#c22) | slide 10 | Report several metrics: PSNR counts pixel error, SSIM looks at structure. |

### Lecture 4.3 · Applications and the road ahead

| # | Concept | Slide | In one line |
|---|---|---|---|
| 23 | [AR occlusion: in front or behind?](https://znjubery.github.io/3DVision2026/module4/#c23) | slide 5 | AR needs good depth exactly where surfaces are close to the virtual object. |
| 24 | [Latency: the picture arrives late](https://znjubery.github.io/3DVision2026/module4/#c24) | slide 6 | Lag = turn speed × latency. Only real-time methods keep it under a few pixels. |
| 25 | [Slice a neural field: a CT scan for plants](https://znjubery.github.io/3DVision2026/module4/#c25) | slide 7 | Query the field anywhere: slicing turns a 3D model into measurements. |
| 26 | [Images + LiDAR: trust each where it is good](https://znjubery.github.io/3DVision2026/module4/#c26) | slide 8 | Weight each sensor by 1/error²; the fused depth beats both. |
| 27 | [Hyperspectral: NDVI from albedo, not raw pixels](https://znjubery.github.io/3DVision2026/module4/#c27) | slide 8 | Store reflectance per band; health indices then stop changing with shadows. |
| 28 | [Dynamic scenes: wind](https://znjubery.github.io/3DVision2026/module4/#c28) | slide 9 | Separate what the leaf is from where it is now. |
| 29 | [Generalization: a prior from many plants](https://znjubery.github.io/3DVision2026/module4/#c29) | slide 9 | A learned prior trades many views per scene for a few numbers per scene. |
| 30 | [Frontiers: generate plants, model growth in 4D](https://znjubery.github.io/3DVision2026/module4/#c30) | slide 10 | Learned priors let models create and track change, not just copy one scene. |

## Using it in class

- **← / →** (or Page Up / Page Down) move between concepts.
- **All 30 concepts** jumps to any concept; the lecture buttons jump to the start of 4.1, 4.2 or 4.3.
- **Projector size** enlarges text and canvases; **Full screen** hides the browser bars.
- Each concept has an everyday analogy, a live demo, an **Ask the class** question with a hidden answer, the math behind a toggle, and a one-line takeaway.

## Publishing

1. Make the repository public: **Settings → General → Danger Zone → Change visibility → Public**
   (on an iPad, open `github.com/znjubery/3DVision2026/settings` in Safari, or use **aA → Request Desktop Website**).
2. Turn on Pages: **Settings → Pages → Deploy from a branch → `main` / `(root)` → Save**.
3. After about a minute the links above go live.

Each page is one self-contained HTML file; it also works when opened straight from a download.
