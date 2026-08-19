---
name: pixel-chibi-avatar-engine
description: Convert an attached real-person photo into a highly recognizable, full-body pixel chibi avatar in the fixed clean style of this skill. Use when a user asks to turn a selfie, outfit photo, portrait, or a person in a photo into a pixel doll, pixel chibi, pixel avatar, 像素小人, 像素人物, or 像素头像—especially when hairstyle, outfit, expression, pose, and an exact sprite-height constraint must be retained.
---

# Pixel Chibi Avatar Engine

Create one full-body, standalone pixel chibi avatar from the user's attached photo. Use the built-in image-generation tool; treat the photo as an identity, clothing, pose, and expression reference, never as a request to reproduce a photorealistic person.

## Non-negotiable visual contract

- Draw one centered character on a pure white background by default. Use a flat chroma-key background only when the user asks for a transparent PNG, then remove it with the standard image-generation workflow.
- Render as deliberately enlarged, crisp square pixels: no smooth painting, blur, vector outlines, 3D, Minecraft geometry, text, watermark, scene, or prop unless it is essential to the original pose.
- Use a compact, cute full-body proportion: head height about 38–43% of the character; short torso and limbs; face made of simple blocks, not realistic anatomy.
- Work on a logical **48 × 64 pixel canvas**. The top of the head/hat/hair to the lowest sole or dress hem must occupy **48 ± 2 logical pixels**; leave at least 6 logical pixels of white breathing room above and below. Keep all limbs inside the canvas.
- Deliver the logical sprite enlarged by nearest-neighbor scaling only. Do not interpolate, anti-alias, or introduce fractional pixel blocks.
- Use soft but readable tonal ramps: usually 3–5 shades for hair and clothing, 2–4 for skin, and large connected clusters rather than speckled noise.

## Preserve the person, in this order

1. Signature silhouette: hair length/volume, bangs/parting, hat, and any immediately recognizable accessory.
2. Pose and expression: retain the action, viewing direction, asymmetry, gesture, and emotional cue. Simplify fingers only after the gesture remains legible.
3. Outfit identity: retain garment type, silhouette, dominant colors, standout pattern placement, shoes, and jewelry/watch/glasses.
4. Facial cues: retain eye shape/direction, eyelid or wink, eyebrow angle, mouth mood, and face framing. Translate them into simple chibi blocks; never invent a generic anime face.
5. Fine detail: simplify texture, tiny logos, and background clutter first—not the above anchors.

When the photo is cropped or the feet are hidden, infer only the missing lower body in the same outfit and keep the result within the height contract. When more than one person is visible, ask which person to convert unless the intended subject is unambiguous.

## Generation procedure

1. Inspect the source and silently make a short identity sheet: hair/hat, face expression, pose, outfit silhouette + palette + motifs, accessories, and shoes.
2. If available, include `references/pixel_style_01.png` and `references/pixel_style_02.png` as **style-only** references. Do not copy their character, clothes, or pose.
3. Generate using this prompt, replacing bracketed fields from the identity sheet:

```text
Use case: stylized-concept
Asset type: full-body avatar sprite
Input image: attached photo is the sole identity, outfit, expression, and pose reference.
Primary request: Transform the pictured person into one highly recognizable cute pixel chibi avatar. Preserve [hair/hat], [expression and gaze], [pose/gesture], [outfit silhouette, colors, motifs], and [accessories/shoes].
Style: clean premium pixel-doll illustration, deliberate chunky square pixel clusters, soft 3–5 shade ramps, minimal dark outline only where needed for silhouette clarity, no texture noise.
Proportions and size: logical canvas 48x64 pixels; character silhouette exactly 48±2 logical pixels tall from head/hat/hair to feet or hem; oversized head about 40% of character height, compact body, short limbs. Enlarge only with nearest-neighbor pixels.
Composition: single centered full-body character, pure white background, generous even margin, no ground shadow.
Identity priority: hair silhouette > pose/gesture > outfit/accessories > eye/expression cues > tiny detail.
Avoid: realistic portrait, generic anime face, default idle pose, changed outfit, missing accessory, extra limbs/fingers, smooth gradients, blur, anti-aliasing, 3D, vector art, text, watermark, background scene.
```

4. Inspect the result before delivering. Regenerate once with a targeted correction if it fails any item below.

## Acceptance checklist

- The person is recognizable at a glance through the hair, expression, pose, and clothing—not merely through a generic cute face.
- The chosen gesture and body direction survive the chibi conversion.
- A hat, hair clip, earrings, watch, glasses, stripes, flowers, or other distinguishing detail is present when visible in the source.
- The character is full-body, centered, and its logical height is 46–50 pixels.
- Pixel blocks are crisp and consistently sized; there is no blur, photorealism, or invented scene.

## Output

Return the final enlarged PNG. State the applied logical canvas and measured character-height target (for example: `48×64 logical pixels; 48-pixel character height`). If the user provides several source photos of the same person, combine only mutually consistent identity traits and use the clearest photo for the requested pose/outfit.
