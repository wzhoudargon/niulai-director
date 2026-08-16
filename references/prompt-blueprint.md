# Prompt blueprint and parameters

Use this reference to convert source analysis and user choices into one executable
image-edit prompt. Replace variables; do not paste the schema into a generation tool.

## Contents

- Parameter schema
- Production and compact prompts
- Negative constraints and text handling
- Source recipes

## Parameter schema

```yaml
skill: niulai-director
preset: primitive_folk_cgi | bright_folk_cgi | sunlit_game_map | community_cgi_stage | rough_night_render
reconstruction_strength: medium | high | extreme
anchor_lock: strict | high
identity_lock: medium | high
detail_budget: very_low | low
geometry: primitive_low_poly | visibly_low_poly
construction: push_pull_primitives | coarse_intersecting_solids
curve_segments: minimal | very_low
surface_finish: hard_faceted | lumpy_crude_smoothing | mixed
face_geometry: clumsy_asymmetric | strongly_faceted | angular_readable
gaze_quality: stiff_misaligned | crude_readable | source_faithful
material_detail: uneven_flat_and_crude_maps | mostly_flat_with_one_crude_map
texture_resolution: very_low | low
texture_mapping: stretched_tiled_misaligned | crude_projection
marking_detail: coarse_painted_or_flat_patches | simplified_flat_patches
component_reuse: heavy | strong | moderate
background_detail: sparse | reduced
lighting: default_viewport_or_naive_single_light | flat_stage_light | hard_awkward_daylight | crude_point_lights
shadows: simple_or_weak | hard_simple | crude_point_shadows
palette: source_anchored_blunt | source_anchored_saturated
post_effects: subtle_capture_softness | none | user_requested_capture_artifacts
text_mode: none | preserve_exact | user_text
ratio: source_ratio | 1:1 | 3:4 | 4:3 | 9:16 | 16:9
```

## Production prompt template

```text
Rebuild the supplied image as a crude homemade primitive 3D animation frame or rough
preview assembled with beginner-level tools. This is not a blur filter, compression
pass, polished retro game asset, or fashionable low-poly illustration.

BROAD ANCHOR LOCK — Preserve [subject count/types], [left-to-right arrangement],
[major pose/gesture], [crop/camera/perspective], [occlusion/depth layers], [scene
category], and [three to six dominant color blocks]. Preserve large silhouettes,
garment categories, and major props. Do not pursue exact fine facial or background
detail; the source should remain recognizable through its large relationships.

DETAIL BUDGET — Use [preset], [reconstruction_strength], and [detail_budget].
Remove subtle facial acting, hair strands, fingers, embroidery, microtexture,
decorative architecture, small signs, and incidental set dressing.

CONSTRUCTION — Rebuild all people, animals, objects, terrain, vegetation, and
architecture with [construction] and [geometry]: a tiny number of boxes, wedges,
tapered prisms, crude extrusions, and low-segment cylinders. Use [curve_segments]
and [surface_finish]. Keep intersecting volumes, hard normals, abrupt contour changes,
visible facets, component seams, lumpy proportions, block joints, wedge hands or
paws, crude face planes, and thick hair blocks. Crude automatic smoothing may make
some bodies swollen and blobby, but do not sculpt, anatomically blend, subdivide in
detail, or professionally clean the topology.

FACES AND GAZE — For faces use [face_geometry] and [gaze_quality]: simple reused
eye construction, unequal eye sizes, slightly off-center pupils, imperfect gaze
convergence, stiff lids, block noses, flat mouth slits, and frozen expressions.
Keep broad intent readable without professional animation polish.

MATERIALS, MARKINGS, AND REUSE — Use [material_detail] and deliberately mix two cheap
treatments: blunt saturated solid colors on some subjects or parts, and one tiny
noisy diffuse image crudely applied to other asset families. Use [texture_resolution]
and [texture_mapping]: visible stretch, tiling, mirroring, projection mismatch,
inconsistent scale, smeared detail, and painted shadow information are desirable.
Ground, hills, rocks, bark, blob foliage, animal bodies, clothing, or walls may use
coarse photo-like or scribbled maps, while muzzles, hooves, hands, eyes, props, or
whole characters remain flat-colored. Use [marking_detail] for identity-critical
patterns. Use [component_reuse] across crude body parts and background objects. No
coherent realistic fur, skin, fabric, grass, facade, or PBR material system.

BACKGROUND — Set [background_detail]. Begin with one ground plane or coarse terrain
mass and keep only essential setting forms. Reuse two or three primitive background
components with minimal variation: cylinder trunks, blob canopies, blunt rocks,
simple hills, posts, boxes, or repeated building bays. Crude ground, bark, foliage,
rock, or wall maps may repeat visibly. Remove unique clutter and atmospheric depth.

LIGHT, RENDER, AND CAPTURE — Use [lighting]: one plain directional or overhead-front
light plus flat ambient fill, with [shadows]. Allow blunt highlights, muddy patches,
weak contact, and inconsistent nearby exposure. Present the scene like a rough
viewport preview or homemade animation render with no beauty finish. Keep
[post_effects] secondary: mild low-resolution softness, compression blur, exposure
drift, or edge vignette may appear, but never invent subtitles, play buttons, screen
borders, gallery arrows, watermarks, or software UI.

OUTPUT — [ratio]. [text instruction].

DO NOT — [source-tailored prohibitions], exact premium reproduction, attractive
aligned eyes, refined facial acting, smooth subdivision, clean designer facets,
high-resolution or cleanly mapped textures, smooth accurate anatomy, rich detailed background, rim light,
beauty light, three-point lighting, volumetric beams, cinematic depth, PBR, glossy
toys, photorealism, modern game polish, deliberate polished retro styling, darkness
as a shortcut, VHS/CRT/glitch/mosaic, random text, UI, characters, props, logos, or
cow traits absent from the source.
```

## Compact prompt

Use only when the editor follows source images reliably:

```text
Rebuild the supplied image as a sincere but technically poor homemade 3D animation frame.
Lock only subject count, broad arrangement, poses, camera, scene category, large
silhouettes, and color blocks; deliberately reduce fine likeness and background
detail. Assemble every form from very few intersecting boxes, wedges, tapered
prisms, crude extrusions, and six-to-ten-sided cylinders. Keep hard facets, abrupt
contours, lumpy crude smoothing, component seams, stiff unequal eyes, crude face
wedges, block hair, and wedge hands or paws. Mix blunt saturated solid colors with
tiny noisy diffuse images crudely stretched, repeated, mirrored, or mis-scaled across
ground, hills, rocks, bark, blob foliage, clothing, walls, or animal bodies. Keep
muzzles, hooves, hands, eyes, props, or some whole subjects flat-colored. Reuse a
tiny component library and reduce the background to coarse terrain plus essential
masses. Use viewport-like or naive single-light rendering, weak or absent shadows,
and mild capture softness. No accurate anatomy, clean UVs, coherent realistic
materials, polished low-poly art, detailed set, PBR, beauty light, invented subtitles,
play buttons, UI, new subjects, props, logos, cows, or horns absent from the source.
```

## Negative constraint block

```text
Avoid: fine likeness; attractive aligned eyes; expressive professional facial
animation; correct smooth anatomy; professionally blended organic masses; detailed
subdivision; clean topology; elegant triangular facets; polished toy forms;
high-resolution textures; clean UVs; consistent texture scale; realistic fur, skin,
cloth, grass, ground, or facade materials; dense accurate
markings; procedural background variety; rich set dressing; cinematic lighting;
three-point light; rim light; soft bounce; global illumination; volumetric fog;
depth of field; premium game graphics; polished retro-game art; photorealism;
darkness or horror as a shortcut; heavy blur; large pixelation; extreme capture
noise; JPEG destruction; VHS; CRT; glitch; invented text, subtitles, play buttons,
UI, logos, characters, or props.
```

## Text handling

- `none` (default): omit incidental signs, subtitles, watermarks, and interface text.
- `preserve_exact`: quote exact source text and inspect character by character.
- `user_text`: include only exact user-supplied text; invent nothing.

## Source recipes

### Portrait or group

Use `community_cgi_stage` for groups and `primitive_folk_cgi` for a single figure.
Lock count, spacing, pose, hair mass, garment categories, and color blocks. Reuse
the same crude body, eye, hand, and hair-block components. Mix flat garment colors
with at most one badly mapped skin, hair, or cloth image per asset family. Emphasize
faceted or swollen heads, stiff gaze, frozen faces, and wedge hands.

### Animal scene

Use `primitive_folk_cgi`. Lock species, count, stance, markings, and composition.
Build torsos from a few intersecting masses, heads from wedges, legs from tapered
prisms, paws or hooves from blunt wedges, and tails from visibly segmented tubes.
Use either a bright flat body or one coarse noisy body map with stretched painted
fur or scale suggestion. Keep muzzles, horns, hooves, paws, or underparts as blunt
contrasting color regions. Never create groomed fur or accurate dense markings.

### Architecture or landscape

Use `sunlit_game_map`. Lock perspective, horizon, landform, massing, and openings.
Build architecture from boxes and push-pull extrusions, terrain from broad stepped
slabs, and vegetation from repeated cylinder trunks and blob canopies. Mix blunt
flat colors with one or two blurry wall, ground, bark, foliage, or rock maps stretched
and repeated at visibly inconsistent scales.

### Lighting-only follow-up

Lock all geometry, materials, poses, and composition. Replace only lighting with
`default_viewport_or_naive_single_light`: plain overhead-front direction, flat
ambient, blunt local color, muddy creases, simple or absent shadows, weak contact,
and uneven exposure.
