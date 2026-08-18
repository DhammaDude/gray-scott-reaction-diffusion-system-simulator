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

### Quantification now available

The simulator now estimates this organization directly. Its lattice diagnostics use a separate lighter-blur local-peak detector and report mean neighbors, a sixfold-order score, bridge intensity between neighboring spot centers, defect rate, and mean spacing. A measured-edge overlay can be toggled on or off, and a `0.5×` to `4×` zoom control makes the weak inter-spot field easier to inspect. Measured edges are matched across detection ticks and briefly faded rather than removed immediately when a spot splits, merges, or momentarily falls below threshold.

These values are operational measurements of the rendered Gray–Scott field, not evidence of literal bonds or a biological network. The edge threshold is derived from the median nearest-neighbor spacing, so the results should be compared across seeds and nearby parameter values rather than treated as universal constants.

### Visual inference reproduced by the app

With the `show inferred neighbor links` overlay enabled, the simulator draws links between the detected spot centers. These links reproduce the regular organization initially inferred by eye: each spot is typically situated within a six-neighbor, triangularly packed arrangement. The visual impression and the operational measurement therefore converge on the same spatial pattern.

The simulator also provides a separate `show inferred hexagonal cells` overlay. It uses the same detected neighbors as the link view and constructs each local cell from the perpendicular bisectors between a spot and those neighbors. In a six-neighbor equilibrium this produces a hexagonal cell; defects can produce non-hexagonal local cells. This tests the possibility that the eye is registering an organization of the low-concentration space between spots rather than literal links between the bright centers.

These overlays represent different hypotheses: center links describe the spot geometry, while hexagonal cells describe a possible organization of the intervening or negative space. Neither is a claim that the colored overlay lines are literal chemical bonds. They are computed structures based on detected peak positions, local spacing, and inferred neighborhood geometry.

### Tests to add

- Render the raw `V` channel in grayscale with no glow, color blending, or interpolation.
- Measure each spot's coordination number and the pattern's sixfold-order parameter.
- Measure the intensity and persistence of the field between neighboring spots.
- Track defects, broken connections, mergers, and births of new spots.
- Compare the lattice across seeds and nearby `F/K` values.
- Extend lineage tracking so a splitting spot can pass identity to two daughter spots.
