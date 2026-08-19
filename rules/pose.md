# PixelChibiAvatarEngine Pose Preservation Rules


## Purpose

This file controls pose conversion.

The generated pixel character must preserve the original person's body posture.

The goal is:

Transform the person's pose into pixel art.

Not:

Create a new default character pose.


---

# Pose Priority
---

# Pose Lock Enhancement v1.1


## Core Requirement


The pixel character must preserve the meaning of the original pose.


The goal is:


same action

+

pixel chibi transformation


Not:


new character with a similar appearance



---

# Action Recognition Priority


Before generating, identify:


- what the person is doing
- why the arms are positioned this way
- the emotional meaning of the pose


Examples:


Photo:

making a heart with hands


Pixel:

must still create a heart gesture.



Photo:

holding a skirt edge


Pixel:

must still hold the skirt edge.



Photo:

covering face with hand


Pixel:

must keep hand near face.



---

# Upper Body Pose Preservation


Upper body has high priority.


Preserve:


- shoulder angle
- arm height
- elbow direction
- hand location
- hand gesture


Do not simplify arms into:

- straight hanging arms
- symmetrical idle pose



---

# Gesture Protection


Hand gestures are identity and emotion features.


Preserve:


- heart gesture
- peace sign
- waving
- holding objects
- touching face


Simplify fingers if needed.

Never remove the gesture.



---

# Body Orientation Lock


Maintain:


- front view
- side view
- three-quarter view
- leaning direction


Do not automatically rotate the character into a front-facing sprite.



---

# Chibi Pose Adaptation


When converting to chibi:


Allowed:


- shorter limbs
- larger head
- simplified anatomy


Not allowed:


- changing the action
- changing body meaning
- replacing pose with default standing



---

# Pose Verification v1.1


Before output:


Check:


✓ Same action?

✓ Same hand gesture?

✓ Same body direction?

✓ Same emotional feeling?


If no:


Regenerate with stronger pose preservation.

Pose is one of the highest priority features.

The system must preserve:


- body direction
- head direction
- arm position
- hand gesture
- leg position
- body leaning
- sitting or standing state


---

# Pose Analysis Process


Before generating:


Analyze the uploaded image:


## 1. Body Orientation


Identify:

- front facing
- side facing
- three-quarter view
- leaning direction


Keep the same orientation.


Example:


Photo:

Person facing slightly left.


Pixel result:

Character should also face slightly left.


Do not:

Force a front-facing character.


---

## 2. Head Direction


Preserve:

- head rotation
- looking direction
- chin angle


Examples:


Looking sideways:

Keep sideways gaze.


Looking down:

Keep lowered head.


Looking up:

Keep raised head.


---

## 3. Arm Position


The arms are important pose indicators.


Preserve:

- arm height
- arm angle
- elbow position
- hand location


Examples:


Photo:

Both arms raised above head.


Result:

Both arms remain raised.


Photo:

One hand touching face.


Result:

Keep hand near face.


Do not:

Replace with idle standing arms.


---

## 4. Hand Gesture


Hands should preserve the meaning of the gesture.


Examples:


Heart hand gesture:

Keep heart shape.


Peace sign:

Keep V gesture.


Holding object:

Keep object interaction.


Simplify hands into pixels.

Do not add:

- extra fingers
- extra hands
- incorrect hand positions


---

## 5. Body Movement


Preserve:

- leaning
- twisting
- weight distribution


Examples:


Photo:

Body leaning forward.


Pixel:

Keep forward leaning.


Photo:

Relaxed pose.


Pixel:

Keep relaxed pose.


---

## 6. Lower Body


Preserve:

- leg spacing
- walking pose
- sitting pose
- skirt/pants silhouette


Do not automatically create:

- symmetrical legs
- standing idle pose


---

# Forbidden Pose Changes


Never convert original pose into:


- RPG idle standing
- front view character
- symmetrical pose
- arms hanging naturally
- generic game sprite stance


---

# Chibi Adaptation Rules


When converting to chibi:


Allowed:

- enlarge head
- shorten limbs
- simplify anatomy


Not allowed:

- remove gesture
- change pose meaning
- redesign body position


---

# Pose Verification


Before final output check:


✓ Is the body direction correct?

✓ Are arms in the correct position?

✓ Is the gesture preserved?

✓ Is the head direction correct?

✓ Does the character express the same action?


If not:

Regenerate while prioritizing pose preservation.
