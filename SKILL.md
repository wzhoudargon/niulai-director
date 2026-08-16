---
name: niulai-director
description: >-
  Directs and reconstructs any supplied image as deliberately crude primitive 3D:
  a few intersecting or lumpy solids, awkward silhouettes, an inconsistent mix of
  flat saturated colors and tiny badly mapped textures, sparse repeated components,
  and bare-bones lighting while preserving the source's broad composition anchors.
  Use when users invoke
  NiuLai Director, niulai-director, 牛来导演, 反向出圈画质, 低画质重制, 粗糙人物低模,
  纯 SU 建模, 草模, 体块建模, 建模视窗, primitive folk CGI, bootleg CGI, or ask
  to make an image look intentionally cheap, awkward, unfinished, poorly modeled,
  and much less faithfully reproduced.
---

# NiuLai Director / 牛来导演

> Core principle: **保留大关系，主动放弃精致还原；让低质量来自整套生产能力，而不是后期滤镜。**

Direct and rebuild the source as a scene assembled by a sincere beginner from a tiny set of
push-pull primitives. Keep the image readable and structurally related to the source
while making construction, proportions, faces, material mapping, component variety,
lighting, and capture visibly crude and homemade.

## Workflow

Track this sequence:

```text
- [ ] 1. Confirm that an input image exists; request one if absent
- [ ] 2. Read explicit parameters and infer the rest from the primitive defaults
- [ ] 3. Extract broad anchors: subject count, layout, pose, camera, color blocks
- [ ] 4. Set a deliberately low detail and fidelity budget
- [ ] 5. Build one source-based image-edit prompt in the required order
- [ ] 6. Generate/edit unless the user asked for prompts or options only
- [ ] 7. Inspect against the inverted quality gate; retry polished results
- [ ] 8. Return the image plus one compact treatment note
```

## Interaction

- Require an input image unless the user explicitly asks for a new scene.
- Execute directly when an image is supplied without parameters or the user says
  “默认”, “你来判断”, or equivalent.
- If the user says “先别生成”, “给方案”, or “让我选”, do not generate. Offer at
  most three distinct directions.
- Ask at most one question only when a missing decision materially changes output.
- Use an image-edit tool that receives the source image. Include every target image
  through the tool's supported reference input.
- Treat this as reconstruction, not compression, pixelation, or a polygon overlay.

## Analyze broad anchors internally

Identify without reporting every item unless asked:

- **Subjects:** count, broad type, silhouette, large hairstyle, garment category,
  dominant color blocks, large props, pose, gesture, and approximate gaze.
- **Composition:** crop, camera height, perspective, horizon, relative scale,
  spacing, foreground/midground/background, and occlusion.
- **Scene:** only the major terrain, architecture, or stage masses required for
  the image to remain recognizable.
- **Palette:** three to six source colors worth retaining.
- **Discardable detail:** fine facial likeness, subtle expression, hair strands,
  embroidery, microtexture, unique background assets, small signage, and decoration.

## Use primitive defaults

Use `primitive_folk_cgi` unless the user requests a gentler translation. Read
[references/style-system.md](references/style-system.md) when selecting another preset.

```yaml
preset: primitive_folk_cgi
reconstruction_strength: extreme
anchor_lock: strict
identity_lock: medium
detail_budget: very_low
geometry: primitive_low_poly
construction: push_pull_primitives
curve_segments: minimal
surface_finish: hard_faceted_or_lumpy_smooth
face_geometry: clumsy_asymmetric
gaze_quality: stiff_misaligned
material_detail: uneven_flat_and_crude_maps
texture_resolution: very_low
texture_mapping: stretched_tiled_misaligned
marking_detail: coarse_painted_or_flat_patches
component_reuse: heavy
background_detail: sparse
lighting: default_viewport_or_naive_single_light
shadows: simple_or_weak
post_effects: subtle_capture_softness
text_mode: none
ratio: source_ratio
```

These are intentional defaults. High facial fidelity, rich backgrounds, unique
materials, smooth organic anatomy, attractive eyes, or professional lighting are
failures unless requested.

## Preserve anchors, not polish

- Strictly preserve subject count, broad left-to-right arrangement, major pose,
  gesture, crop, camera, occlusion, scene category, and dominant color blocks.
- Preserve large identity anchors such as species, hair mass, clothing category,
  and major props. Do not preserve every facial detail by default.
- Permit proportions, facial topology, gaze alignment, garment detail, and surface
  accuracy to become visibly crude while the scene remains legible.
- Raise `identity_lock` to `high` only when the user requests likeness or the task
  is identity-sensitive; reduce reconstruction strength if necessary.
- Do not change a real person's apparent age, ethnicity, body category, pose, or
  relationship to others merely to create the style.
- Add no people, animals, horns, cow traits, weapons, props, logos, subtitles,
  interface, meme text, landmarks, or weather not evidenced by the source.

## Rebuild all production layers

Apply all layers together:

1. **Construction:** assemble every subject from a very small number of boxes,
   wedges, tapered prisms, crude extrusions, and low-segment cylinders. Permit
   intersecting volumes, abrupt silhouette changes, visible facets, and component
   seams. Limited automatic smoothing may create blunt lumpy shells, but do not
   subdivide, sculpt, retopologize, or blend the masses into accurate anatomy.
2. **Faces and gaze:** reuse simple eye construction; allow unequal eye size,
   slightly off-center pupils, imperfect gaze alignment, stiff lids, flat mouth
   slits, and frozen expressions. Keep intent readable, not professionally acted.
3. **Materials:** use an inconsistent low-budget mixture. Leave some subjects or
   parts as blunt saturated solid colors; cover others with one tiny noisy diffuse
   map crudely stretched, repeated, mirrored, or mis-scaled. Keep essential markings
   as oversized flat patches or roughly painted low-resolution shapes. Never use
   coherent realistic fur, skin, fabric, foliage, ground, or facade materials.
4. **Repetition:** visibly reuse the same crude body parts, trees, posts, rocks,
   buildings, props, hair blocks, eyes, or other primitive components.
5. **Background:** reduce the setting to one crude ground plane or coarse terrain
   mass plus the minimum large forms needed for recognition. Reuse lollipop trees,
   blob canopies, rocks, hills, posts, or buildings. Ground, bark, foliage, and rock
   maps may be visibly blurry, stretched, repeated, and inconsistent in scale.
6. **Lighting:** use default viewport or bare-bones single-light illumination: one
   plain sun or overhead-front direction plus flat ambient fill. Keep shadows hard,
   weak, inconsistent, or absent. Allow blunt highlights, muddy patches, and weak contact.
7. **Presentation:** resemble a homemade primitive 3D animation frame, rough preview,
   or direct screen capture rather than a beauty render. Mild low-resolution softness,
   exposure inconsistency, compression, or edge vignette may remain secondary. Never
   invent subtitles, play buttons, projector borders, navigation arrows, or software UI.

Do not use darkness, horror grading, VHS damage, heavy JPEG corruption, or mosaic
as shortcuts. “Bad” must come primarily from limited scene production.

## Build the edit prompt

Read [references/prompt-blueprint.md](references/prompt-blueprint.md) for the full
schema and reusable clauses. Construct prompts in this order:

1. Declare source-based primitive 3D reconstruction.
2. Lock broad anchors and explicitly release fine-detail fidelity.
3. Set primitive preset, extreme strength, and very-low detail budget.
4. Specify coarse intersecting solids, minimal curve segments, hard facets, crude
   faces, eyes, hair blocks, hands, anatomy, and proportions.
5. Mix blunt solid colors with a few tiny, noisy, badly mapped diffuse textures.
6. Strip the background to coarse terrain and a few repeated primitive masses.
7. Specify default viewport or naive single-light rendering and restrained capture softness.
8. State ratio, text behavior, and source-tailored prohibitions.

Prefer observable flaws over labels such as “ugly” or “bad quality”. Mention a
named game, engine, or film only when the user asks; always translate the name into
construction, material, lighting, and rendering properties.

## Inspect and recover

Read [references/quality-and-recovery.md](references/quality-and-recovery.md) before
judging output. Retry whenever the result is too faithful, attractive, detailed,
varied, or professionally lit. In particular, reject results where:

- faces retain polished animation acting or appealing aligned eyes;
- anatomy, curves, terrain, or architecture are smoothly blended and professionally modeled;
- fur, skin, cloth, foliage, ground, facade, or object textures carry coherent realistic detail;
- textures are cleanly mapped, consistently scaled, or supported by polished PBR response;
- every surface has the same professionally coordinated material treatment;
- background objects are numerous, detailed, and individually modeled;
- lighting uses cinematic separation, rim light, soft bounce, or volumetric depth;
- geometry resembles fashionable designer low-poly art;
- the image resembles deliberate polished retro low-poly art rather than amateur CGI;
- the effect is only blur, pixelation, noise, color grading, or screen damage.

On retry, change only the failed dimension and restate all anchor locks. Stop after
two retries unless the user asks to continue.

## Output

For a completed edit, return the generated image and one sentence naming the
preset plus the main retained anchors. Include YAML only when requested.

For prompt-only requests, return one production prompt and one negative block.

## Minimal invocation

```text
/niulai-director
启用 NiuLai Director
把这张图重制成初学者用少量体块和胡乱贴图拼出的粗糙 3D 动画画面
```

```yaml
skill: niulai-director
preset: primitive_folk_cgi
reconstruction_strength: extreme
identity_lock: medium
component_reuse: heavy
material_detail: uneven_flat_and_crude_maps
lighting: default_viewport_or_naive_single_light
ratio: source_ratio
```

**不是做得像“低模艺术”，而是像初学者把少量体块、亮色纯材质、胡乱缩放的模糊贴图和默认灯光勉强拼成一段动画。**
