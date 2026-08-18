# Observations

Working notes from watching the Gray–Scott simulator. These entries distinguish direct visual observations from provisional interpretations and proposed tests.

## 2026-08-18: Six-neighbor spot lattice

### Direct observation

In the `mitosis` regime, after the field settles into an apparently steady arrangement of spots, each visible spot appears to have approximately six nearest neighbors. Faint yellow lines or halos can be seen between the spots when the black-field visual mode is enabled.

The observation was made with the `black field background (V-channel only)` control enabled. The pattern remains visible against a pure black background, rather than only against the default combined color palette.

### Provisional description

The most precise geometric description is a **hexagonally packed spot lattice**, or technically a **triangular lattice of spot centers with sixfold symmetry**. A honeycomb lattice has three nearest neighbors; this pattern appears to have six.

The faint connecting features may be low-amplitude ridges or halos in the shared reaction–diffusion field. They should not yet be described as literal chemical bonds. A useful provisional term is **subthreshold hexagonal coupling structure**.

This kind of organization is compatible with documented Gray–Scott behavior, including hexagonal spot grids, preferred inter-spot spacing, and halo-mediated spatial interactions. See the Gray–Scott pattern discussion in [Munafo (2014)](https://mrob.com/sci/papers/munafo2014-1218.pdf).

### Relation to the detector

The current detector identifies stronger connected regions above its concentration threshold. It can therefore count the spots while ignoring the weaker field between them. The visual lattice may be structurally present without being registered as a separate set of objects.

This observation does not establish that the pattern is alive, directed, or conscious. It identifies a potentially important form of spatial organization that the current detector does not measure.

### Tests to add

- Render the raw `V` channel in grayscale with no glow, color blending, or interpolation.
- Measure each spot's coordination number and the pattern's sixfold-order parameter.
- Measure the intensity and persistence of the field between neighboring spots.
- Track defects, broken connections, mergers, and births of new spots.
- Compare the lattice across seeds and nearby `F/K` values.
- Extend lineage tracking so a splitting spot can pass identity to two daughter spots.
