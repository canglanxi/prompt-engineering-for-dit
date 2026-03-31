```markdown
# AI Image Generation for Beginners: From Shopping List to Visual Design

> This tutorial is based on the DiT model. All demonstrations follow the ＊*tsubaki.2** standard.

Many people encounter a common frustration when using AI to generate images: they write plenty of prompts, but the result always falls short—either flat, strange, or lacking focus.

This usually isn't because the model isn't powerful enough. It's more about a slight misalignment in how we communicate with AI.

This guide offers a simple way to build a new approach. We'll focus on just two things:

1. How to think: design the image instead of listing items
2. How to act: use prompts and simple tools to bring your design to life

---
```

## Part 1: Core Concept – AI Isn't an Artist, It's a Visual Guesser

First, let's establish a key understanding:

> AI image generation doesn't work like a human artist painting stroke by stroke. It's more like a skilled guesser that takes your prompts and gradually infers the most plausible image.

- If you're vague, it's left to guess wildly, and the results can be unpredictable
- If you're precise, it's better able to infer the image you have in mind

That's why we need to shift from making lists to designing the scene.

---
## Part 2: Is Your Prompt a Grocery List or a Visual Designer?

Most people write prompts like this:

```text
a girl, long hair, skirt, night, rain, city
```

This works fine for SD 1.5 or SDXL, but for DiT models—you're just listing unrelated items.

With DiT models (like Tsubaki / Tsubaki.2), you should be telling AI how things should look and where they should be. When given just a list, AI is left to start from scratch.

A Good Prompt Follows a Structure-First Approach

Define the framework first, then add details. The correct order is:

Composition → Lighting → Depth of Field → Angle → Subject → Environment → Details

Let's look at a practical example:

```text
asymmetrical composition, subject on left third, soft side lighting, shallow depth of field with focus on eyes, low angle view, 1girl with long black hair and red dress, standing in a rainy city street, glowing neon reflections on wet pavement
```

What's the Difference?

Approach Characteristics Result
SD / SDXL style Subject and environment first, no spatial sense AI guesses randomly, results inconsistent
Designed approach Composition, lighting, depth of field first AI follows the structural framework, results controllable

Why Does Order Matter?

Because AI generates from whole to part:

· First 20% of the prompt: defines composition, lighting, depth of field—the framework of the image
· Remaining 80%: fills in subject, environment, details—the substance

If the framework is off, no amount of detail will save it. That's why structural descriptions belong at the start.

---
## Part 3: Seven Steps to Design an Image

To switch to a visual designer mindset, just ask yourself seven questions—in order—before writing your prompt. These seven points determine the foundational structure of your image.

1. Composition: How Is the Scene Arranged?

Composition Type Prompt Keyword Use Case
Central composition central composition Stable, stately
Rule of thirds rule of thirds Natural, balanced
Diagonal composition diagonal composition Dynamic, tense
Leading lines leading lines Depth, direction

Choose one composition style.

2. Lighting: Where Is the Light Coming From?

Lighting Type Prompt Keyword Effect
Side light side light Strongest three-dimensionality
Back light / rim light back light, rim light Atmosphere, emphasizes contours
Top light top light Creates sense of pressure
Under light under light Eerie, unnatural

Have one dominant light source. Good lighting lifts the image.

3. Depth of Field: What's Sharp, What's Blurred?

Depth Type Prompt Keyword Effect
Shallow depth of field shallow depth of field Emphasizes subject, cinematic
Deep depth of field deep depth of field Everything sharp, documentary style
Focus on eyes focus on eyes Highly emotional

Pick a focal point and clarify the hierarchy of elements.

4. Angle: From Where Are We Looking?

Angle Prompt Keyword Effect
Eye-level view eyelevel view Natural, relatable
Low angle low angle Subject appears powerful
High angle high angle Subject appears vulnerable

5. Subject: Who's in the Scene?

Describe features, not just the name.

· Instead of: Hatsune Miku
· Write: extremely long teal twintails, black pleated skirt, digital idol aesthetic

Why? DiT models remember combinations of features more than names. Describing features gives you a more accurate rendition of the character you envision.

6. Environment: Where Is This Taking Place?

Simply state the setting: riverside, city street, forest, room…

7. Details: What Special Touches Stand Out?

Props, expressions, weather, atmosphere, etc.

---
## Part 4: A Special Case – Liminal Space

Sometimes what we want isn't a scene with a character, but an atmosphere. Take liminal space—those empty, eerie in-between places: deserted hallways, empty parking lots, a convenience store at dawn.

Scenes like this have an interesting trait: leading lines composition + no human subject. When these two conditions are met, AI naturally moves toward the liminal space zone and generates that distinct uncanny atmosphere.

Comparison Example

Basic approach:

```text
empty hallway, fluorescent light, no people
```

The result might just be an ordinary photo of an empty hallway—without that unsettling quality.

Designed approach (structure-first order):

1. Composition: Leading lines + vanishing point
   leading lines, vanishing point
2. Lighting: Harsh fluorescent light
   harsh fluorescent ceiling light, cold artificial illumination
3. Depth of Field: Everything in focus
   deep depth of field, everything in focus
4. Angle: Surveillance camera angle
   surveillance camera angle, highangle shot
5. Subject: No people
   no people, empty corridor
6. Environment: Abandoned hospital hallway
   abandoned institutional corridor, endless repeating doorways
7. Details: Stagnant air, oppressive silence
   stagnant air, oppressive silence, dusty air particles in light beams

Full Prompt:

```text
leading lines, vanishing point, harsh fluorescent ceiling light, cold artificial illumination, deep depth of field, everything in focus, surveillance camera angle, highangle shot, empty institutional corridor, no people, endless repeating doorways, abandoned hospital hallway, cold clinical color palette, desaturated tones, raytraced reflections on linoleum floor, dusty air particles in light beams, eerie atmosphere, stagnant air, oppressive silence
```

Key Point

When you use leading lines + no people, AI automatically enters liminal space mode and fills in all the related atmospheric details—cold tones, dust, surveillance angles, etc. You didn't write them explicitly, but the model filled them in.

That's the power of designing the image: give the right structural cues, and AI goes exactly where you want it to.

---

## Part 5: Going Further – Locking Structure with ControlNet

So far, we've worked with text alone. But sometimes text isn't precise enough—say you want a very specific pose, or you want the composition to exactly match a movie poster you like.

That's where ControlNet comes in.

What ControlNet Does

The prompt decides what to draw. ControlNet decides how to arrange it.

It's like giving AI a skeleton to follow, ensuring stability and precision from the ground up.

Three Most Common ControlNet Types

Type Function Description
OpenPose Controls pose Reads a skeleton image, matches the pose
Canny / Lineart Controls edges/composition Reads an edge map, inherits composition and outlines
Depth Controls spatial depth Reads a depth map, creates three-dimensional results

Simple ControlNet Workflow

1. Write your prompt (using the seven-step structure)
2. Find a reference image (for pose, composition, or depth)
3. In your image tool (ComfyUI, WebUI), open ControlNet, upload the reference, select the appropriate model (OpenPose/Canny/Depth)
4. Adjust the weight—usually around 0.7 as a starting point (too high may cause inconsistency)

---

## Part 6: Practical Example – From Miku to the Girl by the River

Let's see how this approach plays out in practice.

Goal: Generate an image of Hatsune Miku by the river at night.

SD / SDXL Style Prompt

```text
Miku, night, riverside, anime style
```

For DiT models, this leaves too much to guesswork: pose? lighting? composition? All unknown. The result is a gamble.

Designed Approach (Structure-First Order)

1. Composition: Asymmetrical composition, subject on the left
   asymmetrical composition, subject on left third
2. Lighting: Moonlight, with skin translucency
   ambient moonlight, subsurface scattering lighting
3. Depth of Field: Sharp focus on eyes, background blurred
   sharp focus on eyes, shallow depth of field
4. Angle: Eye-level view
   eyelevel view
5. Subject: Features instead of name
   1girl, extremely long teal hair in twintails, sleeveless white top, black pleated skirt, glossy black thighhigh stockings
6. Environment: Riverside at night
   riverside at night, distant river
7. Details: Looking back, slight smile, reflections on water
   looking back over shoulder, faint smile, faint reflections from the water

Full Prompt

```text
asymmetrical composition, subject on left third, ambient moonlight, subsurface scattering lighting, sharp focus on eyes, shallow depth of field, eyelevel view, 1girl, extremely long teal hair in twintails, sleeveless white top, black pleated skirt, glossy black thighhigh stockings, riverside at night, looking back over shoulder, faint smile, distant river, faint reflections, 16:9
```

---

## Part 7: When to Use Character Names, When Not To

This is a common question. Let's clarify.

When to Avoid Using Character Names Directly

· When using newer DiT models (tsubaki / tsubaki.2) — these are more sensitive to feature combinations, and describing features yields better results
· When you don't want to be locked into training data — character names tend to pull the result toward the most generic version

When It's Okay to Keep Character Names

· When using Stable Diffusion / SDXL — these models have strong name alignment, using the name gives more stability
· When you want 100% accuracy for a specific version — in such cases, using LoRA is more precise
· When combining with negative prompts — e.g., mixing clothing from character A with hairstyle from character B

A Simple Rule of Thumb

Goal Approach
Want the model to be expressive and original Use feature descriptions, not the name
Want the model to replicate a known version reliably Use the name, or better, use LoRA

In our Miku example earlier, we used a combination of features instead of directly writing Hatsune Miku. This keeps the output within the Miku space without locking it into a specific version—resulting in a character that feels recognizable yet fresh.

---

## Part 8: TL;DR – Three Key Takeaways

First: Change Your Mindset

Shift from making a shopping list to designing a visual. Start with structure (composition, lighting, depth of field), then fill in the content (subject, environment, details).

Second: Use the Seven-Step Structure

Every time you write a prompt, run through this order:

Composition → Lighting → Depth of Field → Angle → Subject → Environment → Details

Third: Use Tools When Needed

When text isn't precise enough, lock down the structure with ControlNet. The prompt tells AI what to draw. ControlNet tells AI how to arrange it.

---

## Conclusion

If your AI-generated images aren't turning out the way you want, it's rarely because the model lacks capability. More often, it's because the model hasn't been given a clear framework to work with.

90% of the time, the issue isn't a lack of prompt words—it's the absence of visual structure.

Spend time thinking about the image you want before generation, and your results will become much more consistent.

```
