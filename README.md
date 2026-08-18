# Gray–Scott Reaction–Diffusion System Simulator

A live Gray–Scott reaction–diffusion system simulator that applies a real philosophical criterion — not a metaphor for one — to a physical dissipative structure, frame by frame, and reports what passes.

**[Open `index.html`](./index.html) — no build step, no dependencies. Any browser.**

---

## What this actually is

The simulator runs a [Gray–Scott reaction–diffusion system](https://en.wikipedia.org/wiki/Reaction%E2%80%93diffusion_system): two chemical concentrations diffusing and reacting on a grid, spontaneously relaxing an imposed gradient. This is a textbook instance of what Prigogine called a **dissipative structure** — the same category of physical system underlying the companion paper this project is built from, *"Directedness as Functional Autopoiesis."*

The paper argues that directedness — the kind of minimal "aliveness" separating a starfish from a thermostat — should be identified entirely with a structural, two-part test:

1. **Regeneration** — a system's own components are being actively rebuilt, by itself or genuinely on its behalf.
2. **Boundary maintenance** — a boundary against the environment is actively held, not merely inert.

Satisfy both, and the paper calls that *functional autopoiesis*. Satisfy neither, or only one, and there's nothing there — not a fainter version of directedness, just its absence.

The simulator takes that criterion literally and runs it as code. Every few frames, the simulator:

- flood-fills the concentration field into candidate regions,
- checks each region for a held boundary (a compactness measure — is the edge tight, or bleeding into the surrounding field),
- checks each region against the *previous* detection window for spatial overlap — a proxy for regeneration, since a region that's only a one-frame fluctuation doesn't persist across checks, and a region that's actively rebuilding itself does.

Regions that pass both checks get circled and counted, live, on screen.

## Why this, and not an illustration

An animation of blobs forming and calling it "emergence" would illustrate the paper's vocabulary without testing anything. This does something stricter: it takes the paper's own stated criterion, implements it as an actual classifier, and points it at a real physical process the paper didn't design. If the detector lights up on nothing, or on everything, that's informative — it means the criterion as coded is too strict or too loose, which is a legitimate way to stress-test a philosophical definition against a concrete case.

**What it doesn't do:** the detector is a coarse pixel-level heuristic, not a rigorous implementation of the paper's criterion, and it does not measure first-person character or phenomenal experience. Under the paper's argument, experience is not an additional physical product for the detector to find; it is the first-person character of the world-engaging activity itself. The app is therefore a structural instrument, not empirical proof about phenomenality, and it should not be read as one.

## Using it

- **Presets** jump to known Gray-Scott parameter regimes: `spots` and `mitosis` are the ones worth watching first — mitosis in particular shows regions splitting, the closest this system gets to self-reproduction, an autocatalytic set spending gradient by making more of itself. `turbulent` dissipates the gradient just as fast but structurally resembles a hurricane, not a cell — watch the counter mostly stay at zero there.
- **Pattern vocabulary** keeps the labels precise: `spots` are localized spots, `worms` are worm-like or labyrinthine structures, `mitosis` means self-replicating spots, `solitons` means localized coherent structures, and `turbulent` means spatiotemporal chaos. These are dynamical labels, not claims that the patterns are biological.
- **Lattice diagnostics** use a separate lighter-blur local-peak detector to quantify faint organization between spots: mean neighbor count, sixfold order, bridge intensity, defect rate, and mean spacing. The optional measured-edge overlay makes the inferred connections visible without treating them as literal bonds; tracked edges briefly fade through split/merge detection gaps.
- **Zoom** scales the field from `0.5×` to `4×` so weak halos and inter-spot structure can be inspected more closely.
- **Feed / kill sliders** let you hand-tune the underlying reaction parameters (`F`, `k` in the standard Gray-Scott formulation) if you want to hunt for regimes the presets don't cover.
- **Reseed** restarts the field under the current parameters without changing them.

## Project structure

```
gray-scott-reaction-diffusion-system-simulator/
├── README.md          this file
├── index.html          the simulator — self-contained, no build
└── docs/
    ├── OBSERVATIONS.md  working notes from running the simulator
    └── VISION.md        where this project could go next
```

## Relationship to the paper

This is a companion artifact, not a replacement for the paper's argument. Read [`docs/OBSERVATIONS.md`](./docs/OBSERVATIONS.md) for running observations and [`docs/VISION.md`](./docs/VISION.md) for how the project might grow.
