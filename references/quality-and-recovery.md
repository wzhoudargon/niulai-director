# Inverted quality gate and recovery

Inspect the generated image itself. Success means controlled low production value,
not conventional visual polish.

## Contents

- Hard pass criteria
- Scored checks
- Failure recovery
- Retry discipline

## Hard pass criteria

- **Broad anchor fidelity:** subject count, arrangement, pose, crop, camera, scene
  category, and dominant color blocks remain recognizable.
- **Fidelity ceiling:** fine faces, eyes, hair, hands, garments, and background are
  visibly simplified; a near-exact polished reproduction fails.
- **Primitive geometry:** silhouettes, joints, hands, faces, foliage, terrain, and
  architecture are assembled from a few coarse intersecting solids with visible
  facets or blunt lumpy smoothing, abrupt transitions, and no accurate professional blending.
- **Crude gaze:** character eyes are stiff, slightly unequal or imperfectly aligned,
  and lack professional animation subtlety while remaining non-horrific.
- **Material incoherence:** the scene visibly mixes blunt saturated solid colors
  with a tiny library of noisy diffuse maps stretched, tiled, mirrored, or mis-scaled
  across selected bodies, terrain, trees, rocks, clothing, walls, or props. Clean
  UVs, consistent scale, coherent realistic materials, groomed fur, and PBR fail.
- **Component poverty:** subjects and backgrounds visibly come from a very small
  reused primitive library; detailed unique modeling and set dressing fail.
- **Bare-bones lighting:** illumination is blunt, flat, and simple, with muddy patches,
  simple or absent shadows, weak contact, and no cinematic separation.
- **Amateur presentation:** the result resembles a modeling preview, homemade 3D
  animation frame, or rough screen capture rather than deliberate polished retro art.
  Mild softness or vignette may support the look; invented subtitles, play buttons,
  borders, watermarks, and software UI fail.
- **True reconstruction:** low quality comes from geometry, materials, repetition,
  lighting, and rendering—not only blur, noise, pixelation, or grading.
- **No invention:** add no unrequested subjects, props, horns, cow traits, captions,
  logos, interface, landmarks, or weather changes.

## Scored checks

Score each dimension 0–2. Accept at 14/18 or above only when all hard checks pass.

| Dimension | 0 | 1 | 2 |
|---|---|---|---|
| Broad anchors | lost | partly retained | clearly retained |
| Fidelity ceiling | too exact | mixed | detail clearly reduced |
| Geometry | smooth/polished | mixed | awkward primitive |
| Faces/gaze | refined | partly stiff | crudely convincing |
| Materials | coherent/polished | partly crude | visibly inconsistent flat-and-crude mix |
| Component reuse | rich variety | some reuse | visibly limited primitive library |
| Background | detailed | reduced | sparse and repetitive |
| Lighting | cinematic | simple | naively uneven |
| Amateur render character | polished/design-led | mixed | convincingly homemade preview |

## Failure recovery

### Too faithful, attractive, or polished

Retry with: “Lock only count, layout, pose, camera, scene category, silhouettes,
and large color blocks. Discard fine likeness. Reduce topology, proportions,
facial refinement, garment detail, unique components, and material sophistication.”

### Geometry is still smooth or anatomically refined

Retry with: “Rebuild each subject from a tiny number of visibly intersecting boxes,
wedges, tapered prisms, crude extrusions, and six-to-ten-sided cylinders. Keep hard
facets or blunt lumpy automatic smoothing, abrupt contour breaks, block joints, and
component seams. Remove detailed subdivision, sculpted anatomy, accurate blending,
clean topology, and elegant designer facets.”

### Eyes still look professionally animated

Retry with: “Reuse one crude eye model. Make eye sizes slightly unequal, pupils
off-center, gaze convergence imperfect, eyelids rigid, brows simple, and expression
frozen. Keep it readable and awkward, not grotesque or horrific.”

### Background is too detailed

Retry with: “Delete incidental set dressing. Keep only essential scene masses.
Reuse two or three tree/building/beam/post/rock models many times with minimal
variation. Use one crude stretched ground map and at most one shared noisy map per
tree, rock, or building family. No individually authored clutter or atmospheric depth.”

### Materials or markings are too detailed

Retry with: “Replace the coherent material system with an uneven cheap mixture.
Leave some parts as blunt saturated solid colors. Apply only one tiny noisy diffuse
image per selected asset family and make its stretch, tiling, mirroring, projection
mismatch, and inconsistent scale obvious. Preserve identity-critical patterns as
oversized flat or roughly painted patches. Remove groomed fur, pores, weave, PBR,
clean UVs, and realistic micro-surface detail.”

### Lighting is too professional

Retry with: “Change lighting only. Use one plain overhead-front direction plus flat
ambient, comparable to a default viewport or beginner renderer. Keep hard, weak,
inconsistent, or absent shadows. Allow muddy creases and weak contact. Remove rim, beauty, three-point,
bounce, global illumination, volumetrics, bloom, depth of field, and grading.”

### Result becomes dark, horrific, or grotesque

Restore source-led color and readable exposure. Keep awkward eyes and crude faces
within ordinary stylization. Remove horror grading, extreme distortion, deep black
voids, dramatic fog, and threatening light.

### Broad composition drifts

Restate subject count, approximate coordinates, relative scale, pose, camera height,
horizon, foreground occlusion, and background masses. Say “no reframing, recropping,
camera move, subject merge, or rearrangement.”

### Result looks like a filter

Say: “Rebuild every object as an actual primitive 3D asset. Make low polygon count,
intersecting or lumpy solids, inconsistent flat-and-crude materials, reused components,
and naive lighting visible before adding mild capture softness.”

### Result looks like polished retro-game art

Say: “Remove deliberate designer facets, clean UVs, coherent art direction, polished
shading, and finished asset cleanup. Return to coarse push-pull or lumpy masses,
awkward proportions, a mismatched mixture of saturated flat colors and tiny smeared
maps, obvious component reuse, sparse terrain, and naive preview rendering.”

### Unwanted cows, horns, captions, or UI

Say: “The skill name is not a content instruction. Render only source-evidenced
content. Add no cows, horns, animal traits, meme text, subtitles, watermarks, logos,
HUD, or new props.”

## Retry discipline

1. Restate all broad anchor locks on every retry.
2. Change only the failed dimension.
3. Prefer lowering fine-detail fidelity over weakening composition locks.
4. Stop after two retries unless the user asks to continue.
5. Disclose remaining hard failures rather than calling the result successful.
