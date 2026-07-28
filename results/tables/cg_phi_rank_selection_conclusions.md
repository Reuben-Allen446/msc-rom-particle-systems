## Conclusions

This notebook examined the trade-off between POD representation accuracy and
end-to-end surrogate predictability.

A leakage-free five-fold cross-validation procedure was used. Within every
fold, the mean field and POD basis were calculated using only the fitting
simulations. The held-out validation fields therefore had no influence on
either the reduced basis or the coefficient surrogate.

Increasing the POD rank continually reduced projection error. However, the
end-to-end surrogate error did not decrease monotonically because the
higher-order POD coefficients became increasingly difficult to predict.

Repeated neural-network training across five random initialisations produced
mean validation errors of approximately:

- **0.9216% at rank 4**;
- **0.9222% at rank 6**.

Rank 4 achieved the lowest average repeated-seed validation error and was also
selected by the one-standard-error rule. It is therefore retained as the
training-selected parsimonious model.

On the held-out ten-case dataset:

- the rank-4 neural ROM achieved a mean error of
  **0.9273%** and a maximum error of
  **1.5276%**;
- the rank-6 neural ROM achieved a mean error of
  **0.8393%** and a maximum error of
  **1.3042%**.

The rank-4 test error closely matched its leakage-free validation estimate,
showing that the validation procedure provided a reliable estimate of its
generalisation performance. Rank 6 nevertheless achieved the lower observed
error on the available ten-case test set.

The two models therefore serve different roles:

- **rank 4** is the model selected solely from leakage-free training
  validation and model-parsimony considerations;
- **rank 6** is the energy-threshold baseline and gives the best observed
  performance on the available test cases.

The available results do not establish that one rank is universally superior.
The validation difference between ranks 4 and 6 is extremely small, while the
test set contains only ten cases and had previously been examined during the
rank-6 study. Both models should therefore be retained for external validation
on an independent dataset.

Both models preserve the integrated particle volume accurately. Their mean
relative integrated-volume errors are approximately
**0.00289%** for rank 4 and
**0.00288%** for rank 6. Neither model predicts
volume fractions above one, and the small negative values are negligible
numerical oscillations.

Both reduced-order models have been saved as verified deployable packages.
Reloading the rank-4 package reproduces its original predictions to numerical
precision, while the saved rank-6 package reproduces the previously reported
rank-6 errors. The median scalar online evaluation times are approximately
**0.422 ms** for rank 4 and
**0.426 ms** for rank 6. These timings include
neural coefficient prediction and reconstruction of the complete 10,000-point
field, but they are not yet presented as formal speed-ups relative to the
original particle simulations.

A reproducibility manifest records the software versions, model-selection
settings and SHA-256 checksums of both saved ROM packages.
