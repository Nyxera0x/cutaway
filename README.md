# Cutaway

A cutaway is a machine drawn with its shell opened, so you see the mechanism inside. This is the method for building one as a live 3D film from a single reference image: Claude Code writes every shell, gear and part as three.js code, checks the result against the picture, and films the object taking itself apart. It works for anything with a dense core: robotic animals, engines, drones, devices.

This repository holds the method, not the output:

- the job description Claude reads before every animal;
- the checklist format and a full example;
- every prompt, step by step;
- the corrections that made it work.

There is no code here and no renders. Claude writes the code on your machine from these files.

## What you need

- **Claude Code** on Opus.
- **An image model** (ChatGPT works) for the reference picture.
- **Node.js 20 or newer**, **ffmpeg** and **Python 3** for the video and the sound. Claude Code installs them if you ask.

## How it runs

1. **Generate the reference.** One picture sets the look and nothing else. See [PROMPTS.md](PROMPTS.md), step 1.
2. **Add the job description.** Copy [JOB_DESCRIPTION.md](JOB_DESCRIPTION.md) into your project and point Claude at it before every animal.
3. **Write a checklist for this picture.** 10 to 12 numbered lines on what this one image stands on. See [CHECKLIST.md](CHECKLIST.md).
4. **Run the still loop.** Claude renders a still, stacks it next to the reference and grades every line. It stops after round 2 and waits for you.
5. **Measure.** Dark-pixel share against the reference, and the proportions in numbers. Eyeballing lets a tidy diagram through.
6. **Save every correction** into the job description. [LESSONS.md](LESSONS.md) lists ours.
7. **Film it.** Port the approved film of the animal with the closest body 1:1 and change the body only. Every beat gets its own camera.
8. **Write the short version.** A 10-second version is its own script, never a montage of the long one.
9. **Render frame by frame** and score the sound on the same script.

## Files

| File | What it is |
|---|---|
| [JOB_DESCRIPTION.md](JOB_DESCRIPTION.md) | The brief Claude reads before every animal: the look, the order of work, the camera, the film |
| [CHECKLIST.md](CHECKLIST.md) | How to write a checklist for one picture, a template and a full 12-line example |
| [PROMPTS.md](PROMPTS.md) | Every prompt, from the reference image to the sound |
| [LESSONS.md](LESSONS.md) | Each mistake, what it looked like, and the line it added to the job description |

## What it costs

- A still runs about 400,000 tokens over 3 rounds.
- A film runs another 150,000 to 400,000.
- Run 2 animals at a time, not 4, and look at both after round 2. A note there still changes the outcome; after round 6 it only costs tokens.
- An animal whose body is unlike anything you have filmed costs about twice as much. Pick one close to an approved body, or know the price first.
