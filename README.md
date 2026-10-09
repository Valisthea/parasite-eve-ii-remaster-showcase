<p align="center">
  <img src="media/cover.png" alt="Parasite Eve II Remaster — Aya and Dryfield concept cover" width="100%">
</p>

<p align="center"><sub>AI-generated concept artwork · Visual direction · Not an in-game screenshot</sub></p>

<h1 align="center">PARASITE EVE II · REMASTER</h1>

<p align="center"><strong>A familiar place. Rebuilt down to the details.</strong></p>

<p align="center">Unofficial fan project · Early alpha · Unreal Engine · Made in my spare time</p>

<p align="center"><strong>English</strong> · <a href="README.fr.md">Français</a></p>

I’m rebuilding the world of **Parasite Eve II**, starting with **M.I.S.T.**: its shooting range, service spaces and the small details that make the location recognisable.

The aim is to preserve that familiarity while giving the environment real depth, convincing materials and objects that respond to what happens around them. A surface impact, a broken bottle or a damaged light should leave a visible trace.

This repository is a public progress showcase. The project is an **early development alpha**, with temporary characters and unfinished systems. Rebuilding the entire game is a long-term ambition; the work shown here is centred on M.I.S.T.

<p align="center"><a href="media/wide/mist-view15-16x9.png"><img src="media/wide/mist-view15-16x9.png" alt="Early alpha capture of the M.I.S.T. shooting range, 16:9" width="100%"></a></p>

<p align="center"><sub>Unreal Engine capture · early alpha · temporary characters · 3840 × 2160</sub></p>

## Inside the current alpha

<!-- ALPHA_STATUS_START -->
- **Rebuilt so far:** the M.I.S.T. shooting range, the monitoring room behind its service window and the airlock vestibule with its weapon cabinets, matched against the original fixed views.
- **Environment detail:** work counters and drawer units, cases and ammunition boxes, notice boards and printed notices, overhead fittings, a handgun rack and long-gun cabinets.
- **Materials and lighting:** concrete, painted and worn metal, wood, canvas and glass, with ongoing work on wear, reflections and readability.
- **Environmental reactions:** surface impacts, breakable bottles, physical props, reaction sounds and lights that can be damaged.
- **State tracking:** several object states can be restored within the development session. A complete game-save system remains unfinished.

Performance, collision checks and visual polish are still being worked on. The final characters are not yet integrated: the mannequins are temporary.
<!-- ALPHA_STATUS_END -->

## Original framing, rebuilt environments

<!-- COMPARISONS_START -->
Each board puts the **original** (left) next to the **early alpha** (right) at the same reference framing. Click a board to open the untouched native capture (3840 × 2880). The original is a 320 × 240 reference, enlarged for display only. The characters are temporary mannequins.

[![Shooting range — original (left) and early alpha (right)](media/comparisons/mist-view15-4x3.png)](media/alpha/mist-view15-4x3.png)
*M.I.S.T. shooting range · board 3840 × 2160 · [native capture 3840 × 2880](media/alpha/mist-view15-4x3.png)*

[![Monitoring room — original (left) and early alpha (right)](media/comparisons/mist-pierce-4x3.png)](media/alpha/mist-pierce-4x3.png)
*Monitoring room · board 3840 × 2160 · [native capture 3840 × 2880](media/alpha/mist-pierce-4x3.png)*

[![Airlock vestibule — original (left) and early alpha (right)](media/comparisons/mist-vestibule-4x3.png)](media/alpha/mist-vestibule-4x3.png)
*Airlock vestibule with its weapon cabinets and notice boards · board 3840 × 2160 · [native capture 3840 × 2880](media/alpha/mist-vestibule-4x3.png)*

Early alpha: the character poses are not matched to the originals, and every space will get another detailed pass. More views are added as they are rebuilt.
<!-- COMPARISONS_END -->

### Why also show 16:9?

The original references use **4:3**. They remain the baseline for judging the layout and composition.

The **16:9 image** keeps the same vertical field of view as the 4:3 reference. The centred 4:3 area (2880 of the 3840 pixels) therefore matches the reference framing, and the 480 pixels on each side show additional rebuilt space. The [framing guide](media/wide/mist-view15-guide.png) outlines the 4:3 area; the [native 16:9 capture](media/wide/mist-view15-16x9.png) is published untouched.

[![16:9 capture with the 4:3 reference area outlined](media/wide/mist-view15-guide.png)](media/wide/mist-view15-16x9.png)

The firing range seen from the firing line, with the same 4:3 frame:

[![Firing range — 16:9 with the 4:3 reference area outlined](media/wide/mist-range-guide.png)](media/wide/mist-range-16x9.png)

[More widescreen views: the stands, the monitoring room, the airlock →](docs/GALLERY.md#more-widescreen-views)

## Visual direction

The cover and the character sheets are **AI-generated concept references**, separate from the Unreal captures. They explore a visual direction; they do not show completed, animated game characters. Dryfield on the cover is concept artwork, not a playable area demonstrated by this alpha.

<p align="center">
  <a href="docs/CONCEPTS.md#aya-brea--visual-direction"><img src="media/concepts/aya.png" alt="Aya Brea — AI-generated concept sheet" width="49%"></a>
  <a href="docs/CONCEPTS.md#pierce-carradine--visual-direction"><img src="media/concepts/pierce.png" alt="Pierce Carradine — AI-generated concept sheet" width="49%"></a>
  <a href="docs/CONCEPTS.md#jodie-bouquet--visual-direction"><img src="media/concepts/jodie.png" alt="Jodie Bouquet — AI-generated concept sheet" width="49%"></a>
  <a href="docs/CONCEPTS.md#creature--visual-direction"><img src="media/concepts/creature.png" alt="Creature — AI-generated concept sheet" width="49%"></a>
</p>

<p align="center"><sub>Aya · Pierce · Jodie · Creature — AI-generated concept sheets · Visual direction · Not the implemented characters</sub></p>

[Explore the concept gallery →](docs/CONCEPTS.md)

## What comes next

- Extend M.I.S.T. into its remaining connected spaces.
- Continue improving the environment’s fidelity and interactions.
- Consolidate controls, collisions and performance.
- Return to the characters once the environment work is ready.

The planned text languages are **English and French**. Voice acting and cinematic work are possibilities for a later phase, not current alpha features.

I work on this in my spare time, so there is **no release date or ETA**. No public playable build is included in this repository.

## Feedback welcome

If you know PE2 well, I’d love your thoughts on the lighting, materials, layout and atmosphere. A reference screenshot with a specific observation is especially useful.

[Read the feedback guide](CONTRIBUTING.md) · [Current progress](docs/PROGRESS.md) · [Credits and image notes](NOTICE.md)

*Parasite Eve II is the work of its original creators and rights holders. This is an independent, unofficial fan project with no affiliation or endorsement from Square Enix. This showcase contains project documentation and selected images; it does not distribute the original game or extracted game assets.*
