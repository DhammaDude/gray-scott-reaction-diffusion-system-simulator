# Vision

## The core idea

Most philosophy of mind stays entirely in prose. A definition gets proposed, objections get raised, replies get written — all of it argued, none of it run. The Gray–Scott Reaction–Diffusion System Simulator starts from a different premise: if a criterion for directedness is genuinely structural — stated in terms of regeneration and boundary-maintenance, not in terms of anything felt — then it should be possible to hand that criterion to a machine and watch it get applied to a real physical process, live, with no human in the loop deciding case by case which blob "counts."

That's the whole project. Not a simulation *of* the paper's ideas, dressed up to look like it agrees with them — an actual attempt to operationalize the paper's own Section 3 criterion and see what it does when pointed at something real.

## Why a reaction–diffusion field specifically

Gray-Scott systems are one of the best-studied examples of Prigogine's dissipative structures: cheap to simulate, visually legible, and known to produce a wide range of regimes — from unstable turbulence to stable spots to mitosis-like splitting — depending on two parameters. That range is exactly what's needed to stress-test a binary criterion. A good structural test should light up under some regimes and stay dark under others; if it fired uniformly regardless of regime, that would be a sign the detector isn't measuring anything real.

## Where the current version is honest about its limits

- The "regeneration" check is a persistence proxy (does a region spatially overlap its predecessor a few frames back), not a real accounting of whether the region's constituent matter is being actively rebuilt. A more faithful version would track something closer to component turnover.
- The "boundary" check is a single compactness heuristic (area vs. perimeter), not a measure of whether a boundary is doing real thermodynamic work in the Schrödinger sense the paper actually argues for.
- Detection runs on a coarse, downsampled pass for performance, which will miss small or fast-moving structures.

None of this is dishonesty by omission — the app's footer says outright that this is a structural tool, not a proof, and does not measure first-person character or phenomenal experience. The paper's claim about experience is philosophical rather than a detector variable: experience is the first-person character of world-engaging activity, not an additional property the simulation must separately identify. It is still worth being precise about exactly *how* coarse the current detector is, so future work on it starts from an accurate picture.

## Directions worth pursuing

**A more faithful regeneration measure.** Track actual mass/concentration turnover within a region across frames — how much of what's "inside" the boundary at frame N is different material than at frame N-k — rather than just centroid overlap. This would move the detector from "persists" toward something closer to "is actively rebuilding itself," which is the paper's actual claim.

**A real boundary-work measure.** Rather than a static compactness ratio, measure whether the boundary is doing dissipative work — is there a genuine flux gradient across the region's edge, consistent with Schrödinger's account of a living system exporting entropy across a functioning boundary? This is a much closer match to Section 3's actual argument than the current geometric proxy.

**Historical/novel-structure tracking.** The paper's Section 2 introduces "novel structure" — the historical fact that new kinds of structure keep appearing over time, distinct from any single structure's own properties. A logged, scrollable timeline of *when* new structure-types first appeared in a given run (not just a live count) would let the tool speak to that part of the paper too, not only Section 3's criterion.

**Local feedback, visualized.** Section 2 and 5.8 argue that sufficiently robust structures can locally bias which further structures form nearby, strictly bounded to their own causal neighborhood — never a claim about the field as a whole. A visualization that traces a structure's actual zone of influence over time, and shows where that influence measurably stops, would give that argument something concrete to point to.

**Export for the paper itself.** A "capture this run" feature — parameters, structure count over time, a few representative frames — that produces a citable figure or dataset, so a future draft of the paper could reference actual runs of this tool as a worked example, the way Section 3 currently uses the virocell as a worked biological example.

**A second criterion, run side by side.** Section 4's enactivist argument is philosophically distinct from Section 3's structural criterion. It is not another measurable condition to add to the detector: the argument identifies phenomenal experience with the first-person character of the world-engaging activity already being classified. The app should therefore keep testing the structural criterion while treating the experience claim as an ontological interpretation of that activity, not as a hidden variable waiting to be measured.

## What this project is not trying to do

It is not trying to produce evidence that reaction–diffusion spots are conscious, alive in any richer sense, or evidence that settles the hard problem empirically. It is a tool for testing whether a *structural* definition is well-formed — sharp enough to discriminate, not so loose it fires on everything or so strict it fires on nothing. The paper's philosophical claim is that phenomenal experience is not an extra property produced by this activity, while the app's job is to test the activity's structural organization. The project should stay disciplined about keeping that empirical instrument distinct from the ontological argument it accompanies.
