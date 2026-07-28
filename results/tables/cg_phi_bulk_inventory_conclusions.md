## Conclusions

The supplied bulk dataset contains 100 MercuryCG files covering particle-size
ratios from 1.0 to
2.0. Every bulk file has an exact one-to-one match
with a file in the previously analysed small-species dataset.

Both datasets use the same time-averaged 100-by-100 XZ grid, the same
10,000 spatial points, the same output time and the same 32-column MercuryCG
format. The word *bulk* therefore does not refer to a larger spatial grid or a
larger number of simulations.

The numerical results establish the decomposition

$$
\phi_{\mathrm{bulk}}
=
\phi_{\mathrm{small}}
+
\phi_{\mathrm{large}}.
$$

The inferred large-species field is non-negative across all supplied
simulations. The mean integrated volumes are approximately:

- 565.545686 for the bulk field;
- 282.758160 for the small-species field;
- 282.787526 for the large-species field.

The small and large species therefore contain approximately equal total solid
volumes. Their spatial distributions become increasingly different as the
particle-size ratio increases, which is consistent with size-driven
segregation in the rotating drum.

A processed dataset containing the paired bulk, small and inferred
large-species snapshot matrices has been saved for subsequent reduced-order
modelling. The three matrices have shapes
`(10000, 100)` and share the same parameter and spatial grids.

This bulk dataset is a different physical output from the same 100 underlying
simulations. It can therefore be used to study transfer of the ROM methodology
to bulk and large-species fields, but it is not an independent external test
set for the previously fitted small-species ROM.
