# Development progress

[Back to the project](../README.md) · [Français](PROGRESS.fr.md)

Focus: **M.I.S.T. environment reconstruction**, with a separate **Aya lab** for the playable character. This is a development showcase, not a release certification.

| Area | Current status |
| --- | --- |
| M.I.S.T. spaces | Shooting range, monitoring room and airlock vestibule rebuilt at the original framings; further detail passes and the connected spaces to come |
| Environmental reactions | Implemented in the prototype; heavy-load validation and performance still need work |
| Full game saves | Not complete |
| Aya lab (playable character) | Experimental, in a separate Unreal project: movement, posture, aiming, pistol grip, empty reload and firing feedback work at different levels; the tactical reload and the short inspection still need adapting; [details below](#the-aya-lab--update-of-12-october-2026) |
| Final characters | Not integrated; the lab uses a temporary base model, and Aya’s final look is still being researched |
| English and French text | Planned languages; coverage still needs review |
| Public playable release | None included in this showcase |

Work progresses in focused passes: build, compare, test, then correct. Screenshots demonstrate the visual state of a particular build; they do not establish performance at their image resolution.

There is no release ETA. Voice acting, cinematic work and expansion beyond the current environments are future possibilities, not completed features.

## The Aya lab — update of 12 October 2026

The project is still an alpha. Alongside the M.I.S.T. reconstruction, a separate Unreal lab is now dedicated to the playable character: how Aya moves, stands, aims and handles her pistol, and whether her animations stay in step with what the game is doing. Working in a separate project lets me build and test these systems before they go into the main project.

Three tracks, kept apart:

1. **The M.I.S.T. reconstruction**, shown in the images of this showcase.
2. **The Aya lab’s experimental systems**, described on this page.
3. **The search for Aya’s final look**, still in progress.

The character animated in the lab is a temporary female base model, a third-party asset suited to testing. It is not Aya’s final model. The latest lab work is not integrated into the main project yet, and this update is text only: the new character images are not ready to be shown.

### Movement and presence

The lab covers the basics: standing idle, walking, running, moving while aiming and side steps. These animations are made for the engine’s standard mannequin and transferred onto the female base, so she moves with them.

The transfer brought a flaw with it: her upper back was bent about 17° forward and her neck about 25°, so she looked hunched. A constant correction now straightens her. Her overall lean went from about 10° to under 3°, the same as at rest, and her gaze is level.

When she stands still without aiming, she is no longer frozen. She breathes (about 14 breaths a minute), sways slightly on two rhythms that never quite repeat, and glances in a new direction every few seconds. This layer fades in when she stops and fades out as soon as she moves or aims; her aiming pose blends in and out the same way.

The goal is a character who feels present even when nobody touches the controls. These elements work at different levels in the lab and are still being refined.

### Aiming and holding the pistol

- **In her own hand.** The pistol used to hang from the hand of the invisible animation source, so it floated beside hers. It is now attached to her own hand.
- **Arms and wrists.** A twisting arm and an over-bent wrist are fixed: the barrel lines up with the forearm, and the grip sits in the web of the hand.
- **Her own aiming pose.** Torso upright, head level, arms almost straight, pistol in front of her right eye. Before, she copied the mannequin’s compact pose, which brought the pistol against her face.
- **Fingers and support hand.** The right thumb stays clear of the slide’s path. The index finger rests on the trigger while aiming and along the frame while she handles the weapon. The left hand uses the grip described in shooting manuals: heel of the hand on the grip panel, fingers wrapped under the trigger guard, thumbs pointing forward.
- **Continuity between poses.** Each hand position is computed for the direction the forearm comes from during the gesture, which avoids sudden wrist flips.
- **A closer framing while aiming** is being tried, so the pistol and hands read better. Its settings are provisional: it is a lab test, not the game’s camera system.

Hand poses are computed against the pistol’s actual shape, so the fingers wrap it without passing through it, then judged on in-game images rather than on numbers alone. The goal is a grip that looks like trained handling, not a pose. Aiming up and down is not done yet.

### Reloads and ammunition

Pressing reload does not always do the same thing; it depends on what is left in the weapon:

- **Empty weapon: a full reload.** The slide stays locked back after the last shot, the empty magazine drops to the floor as a physical object, a fresh one comes from the pouch, then releasing the slide chambers a round.
- **Partly used magazine: a tactical reload.** Aya keeps the old magazine, so its remaining rounds are not lost.
- **Full magazine: a short inspection.** The ammunition does not change.

The empty reload has been reworked and checked in game on the current female base. The tactical reload and the short inspection were prototyped on the first test mannequin; they still have to be adapted and refined on this base.

Most of the work is about keeping the hands, the magazine, the slide and the ammunition count in agreement. The weapon’s state only changes at precise moments of the gesture (magazine out, magazine in, weapon ready), each applied once and in order; a repeated or late signal from the animation changes nothing. If a reload is interrupted before the magazine comes out, it is simply cancelled. If it is interrupted midway, the weapon stays open and cannot fire until the reload resumes from the right step. The goal: no round lost or duplicated, and no magazine shown in the wrong place.

### Firing feedback

- **Slide.** It kicks back and returns on every shot, letting the casing out; it stays locked back when the weapon is empty, and the reload releases it. It now moves along the barrel’s axis.
- **Recoil.** While aiming, the arms rise and settle back with a short, spring-like motion. The values come from a physics estimate, not from measurements.
- **Muzzle flash.** A brief flash with a light; its shape, size and brightness vary from shot to shot.
- **Casings.** Each one leaves the ejection port with a slightly different speed and spin, so they do not take the same path or land in the same spot. They bounce, roll and come to rest. Beyond a set number on the floor, the oldest disappear.
- **Empty magazine.** It drops as a physical object during the empty reload.

Together, they give each shot some weight and make the pistol read as a working mechanism. These effects are still in development. The lab has no pistol or casing sounds yet; the M.I.S.T. environment has its own reaction sounds.

### An experimental easter egg

Ask to reload several times while the magazine is already full, and Aya reacts. The camera stays fixed, the rest of the world pauses, and she walks up to the camera, looks into it, pulls the slide back slightly to show the round in the chamber, lets it go and returns exactly to where she stood. The ammunition does not change, and the scene can be skipped.

It is an experiment, not a final cutscene.

### Aya’s final look

The base animated in the lab is only a stand-in. For Aya herself, I have explored several approaches: preparing base models, reworking them in Blender, and conforming them onto a rigged character base. Her likeness, face, hair, clothing, facial rig and some deformations are still to be finalised.

Neither the temporary base nor the [concept sheet](CONCEPTS.md#aya-brea--visual-direction) is the playable final model.

### How it is checked

Two kinds of checks, kept separate.

**Logic tests**, on the ammunition rules alone, without animation. Results recorded in the lab, as of 12 October 2026:

- the reference model of the rules passes 57 scripted scenarios;
- across 72,628 random operations (30 runs), its counting rule never broke: rounds in the weapon, in hand, in reserve and fired always add up to the starting total;
- 33 faults deliberately injected into the model were all caught by the tests;
- the engine (Blueprint) version gives the same results as the reference on the same 57 scenarios and on 14,601 random operations compared step by step.

**In-game checks**, looking at the result in the engine:

- the empty reload plays through on the current base: afterwards, 20 rounds in the weapon, 40 in reserve and one magazine on the floor;
- the easter egg plays from start to finish, with the ammunition unchanged and Aya back at her starting point;
- interruption and resume were tried in game early on, on the first test mannequin;
- over 20 shots, the casings spread over more than a metre.

The lab’s complete automated in-game test suites are written but have not been run yet. The lab as a whole is therefore not fully validated.

### What still needs work

- adapting the tactical reload and the short inspection to the current base;
- hand and forearm twists and contacts (the left forearm twists sharply as the magazine goes in);
- checking that the arms never pass through the torso;
- aiming up and down;
- pistol and casing sounds;
- validating the camera framing;
- Aya’s final look and facial rig;
- full validation in game;
- integration into the main project, later.
