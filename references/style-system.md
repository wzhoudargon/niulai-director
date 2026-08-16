# Style system

Use this reference to choose a preset or tune a difficult source. Define the look
through observable production limits rather than one film, game, engine, or meme.

## Contents

- Visual thesis and eight style pillars
- Presets
- Source adjustments
- Strength and fidelity

## Visual thesis

Aim for **sincere amateur 3D production**: an understandable scene assembled from too
few primitive masses, a mismatched mixture of flat colors and badly mapped tiny
textures, too few reusable components, bare-bones lighting, and a rough preview or
screen-recorded finish. The charm should be accidental, direct, and technically naive.

## Eight style pillars

### 1. Coarse blockout construction

- Build forms from boxes, wedges, tapered prisms, crude extrusions, and cylinders
  with roughly six to ten sides.
- Use intersecting masses, hard normals, abrupt contour changes, visible facets,
  block joints, wedge hands or paws, and crude face planes. Limited crude smoothing
  may produce swollen, lumpy silhouettes with no anatomical control.
- Avoid accurate smooth blending, subdivision detail, sculpted anatomy, clean
  topology, elegant triangular mosaics, designer facets, and polished toy forms.

### 2. Unrefined faces and gaze

- Reuse the same simple eyeball and flat pupil-disc construction across characters.
- Allow unequal eye sizes, slightly off-center pupils, imperfect gaze convergence,
  stiff eyelids, crude brows, flat mouth slits, and frozen expressions.
- Keep the broad emotion readable; remove professional subtle acting and beauty polish.

### 3. Inconsistent material poverty

- Mix two incompatible cheap treatments within the same scene: blunt saturated
  solid colors on some subjects or parts, and tiny noisy diffuse images stretched,
  tiled, mirrored, or mis-scaled across other surfaces.
- Favor one crude map per asset family. Ground, hills, rocks, bark, blob foliage,
  animal bodies, or clothing may carry coarse photo-like or scribbled texture, while
  muzzles, hooves, hands, eyes, props, or entire characters remain flat-colored.
- Preserve necessary markings as oversized flat patches or rough low-resolution
  paint. Avoid coherent realistic fur, pores, fabric weave, grass, or facade detail.

### 4. Obvious component repetition

- Reuse the same crude limb, eye, hair block, tree, bush, post, rock, building bay,
  roof, prop, or furniture component wherever plausible.
- Allow near-identical scale and orientation. Component repetition should reveal a
  tiny modeling library rather than procedural variety.

### 5. Sparse repeated background

- Keep only the minimum large scene masses required to identify the setting.
- Start from one ground plane or coarse hill mass. Reuse two or three tree, bush,
  post, rock, building, beam, or prop components many times. Lollipop trees may use
  cylinder trunks and spherical or irregular blob canopies with the same noisy map.
- Remove small signs, decorative trim, incidental set dressing, and unique clutter.
- Avoid realistic vegetation, detailed environments, atmospheric depth, and clean
  voxel-world regularity.

### 6. Bare-bones lighting

- Prefer one plain directional or overhead-front light plus flat ambient fill,
  comparable to a default viewport or beginner renderer.
- Allow flat local color, clipped foreheads/noses/hands, muddy eye sockets and necks,
  hard simple shadows, absent shadows, weak contact, and exposure mismatch.
- Avoid rim lights, beauty lights, three-point setups, soft bounce, global illumination,
  volumetric beams, bloom, cinematic fog, and carefully shaped facial light.

### 7. Rough preview and capture

- Keep facets, coarse silhouettes, intersections, and component seams readable.
- Present the scene without a beauty-render finish, texture polish, depth of field,
  atmospheric separation, or controlled grading. Mild low-resolution softness,
  compression blur, exposure drift, or edge vignette may support the result.
- Treat subtitles, play buttons, screen borders, gallery navigation arrows, and
  software UI as incidental reference capture, not default style content.

### 8. Plain mood and color

- Anchor three to six large colors in the source, then render them bluntly.
- Favor sincere, homemade, literal, slightly washed-out or overexposed color.
- Keep dark scenes readable. Do not default to horror, sepia, teal-orange cinema,
  dramatic desaturation, or premium atmospheric depth.

## Presets

### `primitive_folk_cgi` — default

For general images, animals, people, landscapes, objects, and mixed scenes.

- extreme reconstruction; medium identity lock; very-low detail budget;
- crude intersecting solids, minimal curve segments, and stiff gaze;
- unevenly mixed flat saturated colors and tiny stretched or repeated diffuse maps;
- heavy component reuse and a sparse massed background;
- viewport-like or naive single light with weak, hard, or absent shadows;
- homemade animation-preview quality that remains readable.

### `bright_folk_cgi`

Use when the user wants more likeness or a gentler result.

- high reconstruction; high identity lock;
- readable angular faces with fewer intentional gaze errors;
- the same coarse block construction with slightly clearer silhouettes;
- flat colors mixed with restrained crude maps, limited components, and bright
  simple viewport daylight.

### `sunlit_game_map`

For architecture, streets, travel photos, and spatial scenes.

- boxes and crude extrusions for massing, openings, roads, and terrain steps;
- one or two blurry facade, ground, rock, or vegetation maps stretched and repeated
  across crude boxes and terrain, mixed with blunt flat-color surfaces;
- very small component library and sparse set dressing;
- blunt sky light plus one direction light; simple or absent shadows;
- no automatic dark industrial mood.

### `community_cgi_stage`

For portraits, dialogue, group shots, performances, and frontal compositions.

- exact head count and spacing; medium identity lock;
- shared crude body, eye, clothing-solid, and hair-block components; stiff hands and
  frozen expressions;
- shallow staged depth and repeated beams/backdrops;
- plain overhead-front light, uneven faces, and no cinematic separation.

### `rough_night_render`

Use only for genuine night sources or explicit night requests.

- a few crude point lights, short falloff, hard simple shadows, and dark gaps;
- a few repeated flat emissive-color components or crude emissive maps; readable local colors;
- no horror treatment unless requested.

## Source adjustments

| Source | Lock | Deliberately reduce | Primitive construction |
|---|---|---|---|
| Portrait | silhouette, head angle, hair mass, clothing blocks | face planes, eye alignment, skin detail, hands | faceted or lumpy head, wedge nose, block hair, prism limbs, flat colors plus at most one crude skin/cloth map |
| Group | count, spacing, gestures, color blocks | individual acting, fingers, garment detail | reuse the same body, eye, hand, hair, and clothing-block components |
| Animal | species, essential markings, stance, muzzle direction | fur, paws, joints, muscle anatomy | intersecting or lumpy torso masses, wedge head, prism legs, segmented tail, flat muzzle/hooves, one crude body map or oversized markings |
| Landscape | horizon, landform, palette | foliage variety, rock detail, atmosphere | broad terrain mass with one badly scaled ground map; repeated trunk-and-blob trees, bushes, and rocks sharing crude maps |
| Architecture | massing, openings, perspective | trim, glass, facade detail, clutter | boxes, push-pull extrusions, repeated bays, crude roof slabs, flat colors mixed with stretched wall maps |
| Food/object | silhouette, count, arrangement | curves, labels, microtexture, reflections | stacked boxes, wedges, low-segment cylinders, blunt colors, and at most one coarse diffuse map per asset family |

## Strength and fidelity

- `medium`: recognizable and restrained; use only when likeness dominates.
- `high`: every object reads as rebuilt low-poly; detail remains moderately faithful.
- `extreme` (default): preserve broad anchors only; use primitive geometry, repeated
  components, inconsistent flat-and-crude materials, sparse masses, stiff gazes,
  and bare-bones lighting.

Use `identity_lock: medium` by default. Raise to `high` only for explicit likeness;
never lower broad composition and subject-count locks.
