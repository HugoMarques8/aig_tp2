# Prompt-Inversion Results: Text-only vs Vision LLM Refinement

Comparison of the Part-2 refinement loop using a **text-only** LLM (`llama3.1:8b`, reads the metric-feedback string only) vs a **vision** LLM (`llava`, additionally *sees* the target image and the current render).

- **Objective** = CLIP - LPIPS - RMSE (higher is better)
- **CLIP**: image-image cosine similarity (higher better) | **LPIPS**: perceptual distance (lower better) | **RMSE**: pixel error (lower better)

## Top-3 prompts per target (per system)

For each target, the 3 best distinct prompts found by each system (text-only and vision), ranked by objective.

### 1159_25.png

**Text-only (`llama3.1:8b`)**

| Rank | Iter | Objective | CLIP | LPIPS | RMSE | Prompt |
|---|---|---|---|---|---|---|
| 1 | 3 | +0.441 | 0.930 | 0.350 | 0.139 | a glass of orange juice with a slice of orange on the side, high detail, unsplash 4k render quality, canon eos 5d camera, soft warm natural light with subtle golden undertones, shallow depth of field, napa valley background with minimal foliage, ad image style with vibrant colors and crisp textures. |
| 2 | 2 | +0.227 | 0.928 | 0.504 | 0.197 | a glass of orange juice with a slice of orange on the side, high detail, unsplash 4k render quality, canon eos 5 d camera, soft natural light, warm golden tones, shallow depth of field, napa valley background, ad image style, featured on dribbble. |
| 3 | 1 | +0.214 | 0.921 | 0.509 | 0.198 | there is a glass of orange juice with a slice of orange on the side, unsplash 4k, ps5 render quality, by Antoni Brodowski, post-processing. high detail, scp-914, taken with canon eos 5 d, soymilk, 3d rendering, napa, ad image, featured on dribble, bolero, recipe |

**Vision (`llava`)**

| Rank | Iter | Objective | CLIP | LPIPS | RMSE | Prompt |
|---|---|---|---|---|---|---|
| 1 | 3 | +0.442 | 0.946 | 0.359 | 0.145 | there is a glass of freshly squeezed orange juice with a slice of orange on the side, unsplash 4k, ps5 render quality, by Antoni Brodowski, post-processing. high detail, soymilk, cgsociety 9, inspired by Perle Fine, high quality topical render, akiman, malt |
| 2 | 1 | +0.292 | 0.932 | 0.457 | 0.183 | there is a glass of orange juice with a slice of orange on the side, unsplash 4k, ps5 render quality, by Antoni Brodowski, post-processing. high detail, soymilk, cgsociety 9, inspired by Perle Fine, high quality topical render, akiman, malt |

### 1159_29.png

**Text-only (`llama3.1:8b`)**

| Rank | Iter | Objective | CLIP | LPIPS | RMSE | Prompt |
|---|---|---|---|---|---|---|
| 1 | 1 | +0.135 | 0.923 | 0.595 | 0.193 | arafed palm tree on a rock in the ocean at sunset, adventure hyper realistic render, photoreailstic, an enormous silver tree, puddles of turquoise water, the sun is shining. photographic, long exposure photograph, in matte painting, flooding, inspired by Andrey Esionov, photographic print, high definition photo, old tree, wavy water, paradise |
| 2 | 2 | +0.037 | 0.896 | 0.643 | 0.216 | A majestic silver palm tree stands on a rugged rock in the ocean at sunset, with puddles of turquoise water reflecting the warm sunlight and wavy waves gently lapping against the shore, captured in a high definition photograph with long exposure and subtle lens flares. |
| 3 | 3 | +0.030 | 0.890 | 0.646 | 0.214 | A majestic silver palm tree stands on a rugged rock in the ocean at sunset with warm golden light casting long shadows and gentle waves lapping against the shore amidst calm turquoise water reflecting subtle lens flares. |

**Vision (`llava`)**

| Rank | Iter | Objective | CLIP | LPIPS | RMSE | Prompt |
|---|---|---|---|---|---|---|
| 1 | 1 | +0.156 | 0.933 | 0.578 | 0.199 | arafed palm tree on a rock in the ocean at sunset, adventure hyper realistic render, photoreailstic, an enormous silver tree, puddles of turquoise water, the sun is shining. photographic, long exposure photograph, in matte painting, flooding, inspired by Andrey Esionov, photographic print, high definition photo, old tree |
| 2 | 2 | +0.146 | 0.909 | 0.573 | 0.190 | arafed palm tree on rock in ocean at sunset, adventure hyper realistic render, photorealstic, enormous silver tree, puddles of turquoise water, the sun is shining, long exposure photograph, high definition photo, old tree |

### 1159_3.png

**Text-only (`llama3.1:8b`)**

| Rank | Iter | Objective | CLIP | LPIPS | RMSE | Prompt |
|---|---|---|---|---|---|---|
| 1 | 1 | +0.161 | 0.864 | 0.513 | 0.190 | anime character with a sword and fire in his hand, trending on artstaton, glowing effect, looking like annie leonhart, inspired by Mandy Jurgens, kerberos, spectral, terada, avatar with a blond hair, by Joong Keun Lee, test subject supersoldier, swirls of fire, ash, in the style of clint cearley |
| 2 | 3 | +0.092 | 0.823 | 0.521 | 0.210 | Anime character with a sword and flames in hand, trending on ArtStation, vibrant colors reminiscent of Mandy Jurgens' style, soft warm lighting like Joong Keun Lee's avatar illustrations, dynamic action scene textures with swirling ash and ember effects, Clint Cearley-inspired glowing effect. |
| 3 | 2 | +0.031 | 0.771 | 0.533 | 0.206 | anime character with a sword and fire in hand, trending on artstation, glowing effect, inspired by Mandy Jurgens' style of vibrant colors and soft lighting, reminiscent of Joong Keun Lee's avatar illustrations, with swirling ash and ember textures, in the style of Clint Cearley's dynamic action scenes. |

**Vision (`llava`)**

| Rank | Iter | Objective | CLIP | LPIPS | RMSE | Prompt |
|---|---|---|---|---|---|---|
| 1 | 2 | +0.167 | 0.837 | 0.499 | 0.172 | anime character with sword and fire, inspired by Mandy Jurgens, kerberos, spectral, terada, avatar with blond hair, by Joong Keun Lee, test subject supersoldier, swirls of fire, ash, in the style of clint cearley |
| 2 | 1 | +0.163 | 0.866 | 0.513 | 0.190 | anime character with a sword and fire in his hand, trending on artstaton, glowing effect, looking like annie leonhart, inspired by Mandy Jurgens, kerberos, spectral, terada, avatar with a blond hair, by Joong Keun Lee, test subject supersoldier, swirls of fire, ash, in the style of clint cearley |

### 1159_7.png

**Text-only (`llama3.1:8b`)**

| Rank | Iter | Objective | CLIP | LPIPS | RMSE | Prompt |
|---|---|---|---|---|---|---|
| 1 | 4 | -0.104 | 0.672 | 0.591 | 0.185 | there is a small hedgehog sitting on top of a block of cake with a soft pastel color palette and subtle dry brushing effects, hyper realistic 3d render with intricate fractal hair, gentle thunderbolt lightning illuminates the scene from above with a soft focus crt filter, marvelous designer 3d rendered in pivix style inspired by Gu Hongzhong |
| 2 | 5 | -0.211 | 0.583 | 0.597 | 0.197 | there is a small hedgehog sitting on top of a block of cake with a soft pastel color palette and subtle dry brushing effects, gentle thunderbolt lightning illuminates the scene from above with a soft focus crt filter, intricate fractal hair with detailed texture and subtle shine, marvelous designer 3d rendered in pivix style inspired by Gu Hongzhong |
| 3 | 3 | -0.212 | 0.556 | 0.576 | 0.192 | there is a small hedgehog sitting on top of a block of cake with a vibrant pastel color palette and subtle dry brushing effects, hyper realistic 3d render, soft focus crt filter, gentle thunderbolt lightning illuminates the scene from above, intricate fractal hair, marvelous designer 3d rendered, pivix, inspired by Gu Hongzhong |

**Vision (`llava`)**

| Rank | Iter | Objective | CLIP | LPIPS | RMSE | Prompt |
|---|---|---|---|---|---|---|
| 1 | 2 | -0.039 | 0.613 | 0.511 | 0.142 | boris vallego, citrinitas, moist, crt filter, reluvy5213, fotorealistic |
| 2 | 1 | -0.156 | 0.599 | 0.565 | 0.191 | there is a small hedgehog sitting on top of a block of cake, hyper realistic 3 d render, translucent cube, feathery fluff, marvelous designer 3d rendered, boris vallego, citrinitas, 1 9 8 0 s cgi, mowhawk, nimbus, [ moist, crt filter, reluvy5213, fotorealistic |

### 7836.png

**Text-only (`llama3.1:8b`)**

| Rank | Iter | Objective | CLIP | LPIPS | RMSE | Prompt |
|---|---|---|---|---|---|---|
| 1 | 3 | +0.217 | 0.870 | 0.514 | 0.139 | astronaut standing on a distant planet's rugged terrain with vibrant aurora swirling in the background, hq digital artwork of an expansive view through a worn, dusty lens, explorers' portrait of a dreamer amidst an otherworldly landscape. |
| 2 | 1 | +0.210 | 0.833 | 0.476 | 0.147 | astronaut standing on the surface of a planet with a bright light shining in the background, hq artwork, lost in the milky void, promotional artwork, expansive view, explorers, halo, portrait of a dreamer |
| 3 | 2 | +0.192 | 0.798 | 0.482 | 0.124 | astronaut standing on the surface of a distant planet with a vibrant aurora shining in the background, hq digital artwork, lost in the milky void, expansive view through a worn lens, explorers' portrait of a dreamer amidst an otherworldly landscape. |

**Vision (`llava`)**

| Rank | Iter | Objective | CLIP | LPIPS | RMSE | Prompt |
|---|---|---|---|---|---|---|
| 1 | 1 | +0.210 | 0.833 | 0.476 | 0.147 | astronaut standing on the surface of a planet with a bright light shining in the background, hq artwork, lost in the milky void, promotional artwork, expansive view, explorers, halo, portrait of a dreamer |

### 9338.png

**Text-only (`llama3.1:8b`)**

| Rank | Iter | Objective | CLIP | LPIPS | RMSE | Prompt |
|---|---|---|---|---|---|---|
| 1 | 3 | +0.105 | 0.833 | 0.527 | 0.201 | painting of a majestic mouse with iridescent scales and fluffy tail, inspired by Chris Rahn's intricate textures and Olha Darchuk's whimsical style, colossal quokka-like features in warm golden light, amidst wispy puffs of colored smoke, full art, by Ross Tran. |
| 2 | 2 | +0.097 | 0.783 | 0.533 | 0.153 | painting of a majestic mouse with iridescent scales and fluffy tail, inspired by Chris Rahn's textures and Olha Darchuk's style, colossal quokka-like features, in the warm glow of puffs of colored smoke, full art, by Ross Tran. |
| 3 | 1 | +0.040 | 0.780 | 0.545 | 0.195 | painting of a mouse with a colorful tail and tail, inspired by Chris Rahn, crystalized scales, npc with a saint\'s halo, colossal fluffy tardigrade, in the style of ross tran, the squirrel king, full art, by Olha Darchuk, puffs of colored smoke, quokka, furry fluffy iridescent dragon |

**Vision (`llava`)**

| Rank | Iter | Objective | CLIP | LPIPS | RMSE | Prompt |
|---|---|---|---|---|---|---|
| 1 | 2 | +0.067 | 0.817 | 0.550 | 0.200 | painting of a mouse with a colorful tail and tail, inspired by Chris Rahn, crystalized scales, npc with a saint's halo, colossal fluffy tardigrade, in the style of ross tran, the squirrel king, full art, by Olha Darchuk, puffs of colored smoke, quokka, furry fluffy iridescent dragon |
| 2 | 1 | +0.035 | 0.776 | 0.546 | 0.195 | painting of a mouse with a colorful tail and tail, inspired by Chris Rahn, crystalized scales, npc with a saint\'s halo, colossal fluffy tardigrade, in the style of ross tran, the squirrel king, full art, by Olha Darchuk, puffs of colored smoke, quokka, furry fluffy iridescent dragon |

## Summary (best per target)

| Target | Mode | Iters | Objective | CLIP | LPIPS | RMSE |
|---|---|---|---|---|---|---|
| 1159_25.png | text | 5 | +0.441 | 0.930 | 0.350 | 0.139 |
| 1159_25.png | vision | 5 | +0.442 | 0.946 | 0.359 | 0.145 |
| 1159_29.png | text | 3 | +0.135 | 0.923 | 0.595 | 0.193 |
| 1159_29.png | vision | 3 | +0.156 | 0.933 | 0.578 | 0.199 |
| 1159_3.png | text | 3 | +0.161 | 0.864 | 0.513 | 0.190 |
| 1159_3.png | vision | 4 | +0.167 | 0.837 | 0.499 | 0.172 |
| 1159_7.png | text | 6 | -0.104 | 0.672 | 0.591 | 0.185 |
| 1159_7.png | vision | 4 | -0.039 | 0.613 | 0.511 | 0.142 |
| 7836.png | text | 5 | +0.217 | 0.870 | 0.514 | 0.139 |
| 7836.png | vision | 3 | +0.210 | 0.833 | 0.476 | 0.147 |
| 9338.png | text | 5 | +0.105 | 0.833 | 0.527 | 0.201 |
| 9338.png | vision | 4 | +0.067 | 0.817 | 0.550 | 0.200 |

### Averages

| Mode | Avg iters | Avg objective | Avg CLIP | Avg LPIPS | Avg RMSE |
|---|---|---|---|---|---|
| text | 4.5 | +0.159 | 0.849 | 0.515 | 0.174 |
| vision | 3.8 | +0.167 | 0.830 | 0.495 | 0.168 |

## Source runs

- text / 1159_25.png: `students/outputs/20260527-211005_ollama_refine/refine_loop.json`
- vision / 1159_25.png: `students/outputs/20260607-143011_ollama_vision_refine/refine_loop.json`
- text / 1159_29.png: `students/outputs/20260527-211057_ollama_refine/refine_loop.json`
- vision / 1159_29.png: `students/outputs/20260607-143208_ollama_vision_refine/refine_loop.json`
- text / 1159_3.png: `students/outputs/20260527-211117_ollama_refine/refine_loop.json`
- vision / 1159_3.png: `students/outputs/20260607-143235_ollama_vision_refine/refine_loop.json`
- text / 1159_7.png: `students/outputs/20260527-211141_ollama_refine/refine_loop.json`
- vision / 1159_7.png: `students/outputs/20260607-143317_ollama_vision_refine/refine_loop.json`
- text / 7836.png: `students/outputs/20260527-211245_ollama_refine/refine_loop.json`
- vision / 7836.png: `students/outputs/20260607-143416_ollama_vision_refine/refine_loop.json`
- text / 9338.png: `students/outputs/20260527-211326_ollama_refine/refine_loop.json`
- vision / 9338.png: `students/outputs/20260607-143503_ollama_vision_refine/refine_loop.json`
