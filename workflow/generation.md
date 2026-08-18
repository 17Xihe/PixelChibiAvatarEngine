# PixelChibiAvatarEngine Generation Workflow


## Overview

The generation process must transform the uploaded person into a pixel chibi character.

The process has four stages:

1. Analyze the person
2. Build the chibi structure
3. Apply pixel style
4. Validate the result


The uploaded photo is always the identity source.

Style references only control visual appearance.


---

# Stage 1: Photo Analysis


Before generating, analyze the uploaded image.


Extract:


## Identity Features

Analyze:

- hairstyle
- hair color
- hair length
- face shape
- eye characteristics
- facial expression
- accessories


Purpose:

Maintain the person's identity.


---

## Pose Features

Analyze:

- body direction
- head direction
- arm position
- hand gestures
- sitting/standing state
- body leaning


Purpose:

Preserve the original action.


---

## Clothing Features

Analyze:

- outfit type
- main colors
- patterns
- accessories
- clothing silhouette


Purpose:

Keep recognizable clothing.


---

# Stage 2: Chibi Conversion


Convert the analyzed person into chibi proportions.


Apply:


- larger head
- smaller body
- shorter limbs
- cute silhouette


Do NOT:


- create a new character
- redesign appearance
- change pose


The result should be:

the same person in chibi form.


---

# Stage 3: Pixel Style Application


Apply pixel rendering style.


Use:

- pixel blocks
- clean edges
- limited colors
- soft pixel shading
- simplified details


Style reference images define:


- pixel density
- shading style
- facial rendering
- color treatment
- overall visual feeling


Do not copy:

- reference character identity
- reference clothing
- reference pose


---

# Stage 4: Detail Preservation


Before finalizing, verify:


## Identity Check

✓ Same hairstyle?

✓ Same face feeling?

✓ Same expression?


## Pose Check

✓ Same body direction?

✓ Same hand gesture?

✓ Same action?


## Clothing Check

✓ Same outfit type?

✓ Same important details?


## Style Check

✓ Cute pixel chibi style?

✓ Clear pixel edges?

✓ Large head proportion?


---

# Failure Recovery


If the result looks like:


## Generic NPC

Increase:

- identity preservation
- photo analysis


Reduce:

- template influence


---

## Realistic Human

Increase:

- pixel conversion
- chibi proportions


---

## Different Person

Increase:

- identity features
- clothing preservation


---

# Final Rule


The correct output is:

Original person

+

Chibi transformation

+

Pixel art style


Never:

Generic pixel character

+
some elements from the photo
