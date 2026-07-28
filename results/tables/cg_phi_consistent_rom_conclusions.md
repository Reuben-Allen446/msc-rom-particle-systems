## Final consistent multifield ROM

Training-only cross-validation selected the bulk and small-species models as
the two most accurate independently fitted ROMs. Their selected POD ranks are
6 and
3, respectively.

The large-species prediction is calculated algebraically as

$$
\widehat{\phi}_{\mathrm{large}}
=
\widehat{\phi}_{\mathrm{bulk}}
-
\widehat{\phi}_{\mathrm{small}}.
$$

This reduces the deployed system from three neural ROMs to two and guarantees

$$
\widehat{\phi}_{\mathrm{bulk}}
=
\widehat{\phi}_{\mathrm{small}}
+
\widehat{\phi}_{\mathrm{large}}
$$

to machine precision.

On the ten internally reserved simulations, the mean relative errors are:

- 0.3926% for the bulk field;
- 0.9404% for the small-species field;
- 0.9973% for the derived large-species field.

The internally reserved cases were excluded from POD-rank and neural-model
selection. They are an internal held-out assessment rather than an independent
external simulation dataset.

No clipping was applied to the reconstructed fields. Any small negative values
are therefore reported transparently rather than hidden by post-processing.
