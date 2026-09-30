# Write a specification for one increment

A useful spec lets someone distinguish acceptable behavior from a plausible mistake. Write enough to guide the next increment of your project and check its result.

## Start with a decision

Name the project's purpose, then describe the next piece of work in enough detail to judge its result. For an image-editing project, changing one object's color is a smaller task than building a complete editing system. You can write the spec before you have an implementation.

Describe behavior separately from implementation. “Keep the jacket's logo unchanged” specifies behavior. “Use a segmentation model” chooses an implementation. Include an implementation constraint when it serves a concrete purpose, such as requiring code to run on the hardware you have.

For a software component, decide whether an input restriction is the caller's responsibility or a case the function promises to reject. Those are different contracts.

## A reusable template

Copy these six fields into your repository and fill them for your increment.

```text
Purpose and scope:
What decision or next step will this support? What fits in this increment?

Inputs and outputs:
What do you supply, and what result should the project produce?
State shapes, units, and types where they matter.

Required behavior:
What must happen on ordinary inputs, boundaries, and invalid inputs?
What must remain unchanged?

Examples and acceptance checks:
Give a small input with an expected result and explain its basis.
Name a plausible mistake that each check would catch and what it cannot settle.
For a qualitative result, say what a reviewer should inspect.

Assumptions and open questions:
What are you taking as given? Which decisions still need an answer?
Decide which questions must be settled before the next increment can proceed.

Implementation constraints:
State required dependencies or interfaces and why they matter.
Leave other implementation choices open.
```

Expose vague words by asking two people to interpret them on the same case. “Preserve the jacket's appearance” might permit changing a logo's color or require leaving it alone. Decide whether the distinction matters to your project. A spec can permit several acceptable outputs without being ambiguous about what is acceptable.

If you cannot yet choose a numerical measure, describe what you can inspect and what remains uncertain. Do not invent a threshold to make the spec look complete. For “fast,” name a workload and a time limit when you can justify them, or record what you need to measure first.

## Optional worked spec for a NumPy standardizer

This numerical example shows the six fields for a small software component. Use it if it helps with your task; Lab 3 does not require a normalization build.

**Purpose and scope.** Standardize numeric features for a model experiment using statistics fitted on training rows. This increment provides fitting and transformation. File loading and missing-value imputation are separate work.

**Inputs and outputs.** `fit_standardizer(X_train)` returns `(mean, scale)`, two NumPy float64 vectors with one entry per column. `standardize(X, mean, scale)` returns a new float64 matrix with the same shape as `X`. It accepts the statistics returned by fitting.

Both matrices contain finite real numeric values, with at least one row and one column. Transform inputs have the same column count as the training matrix. Reject a non-matrix, an empty dimension, a non-finite value, or a mismatched column count with `ValueError`.

**Required behavior.** Compute each training column's mean and population standard deviation, dividing the squared deviations by the number of rows. Set a zero standard deviation to 1. Transform each value as `(value - mean) / scale`. Use the fitted statistics unchanged for every transformation. Preserve the supplied arrays. A row's result is independent of other rows in its transformation batch.

**Examples and acceptance checks.** Use these training rows.

```text
[[1, 10],
 [3, 10],
 [5, 10]]
```

The mean is `[3, 10]`. The first column's squared deviations sum to 8, so its variance is `8/3`. The fitted scale is `[sqrt(8/3), 1]`. The transformed training rows are `[-sqrt(1.5), 0]`, `[0, 0]`, and `[sqrt(1.5), 0]`.

A validation row `[7, 12]` becomes `[sqrt(6), 2]`, approximately `[2.449489743, 2]`. The constant training column becomes 2 for this validation row because the chosen rule uses scale 1. Recomputing statistics on validation rows would violate the spec.

These checks use the required interface.

```python
import numpy as np

train = np.array([[1., 10.], [3., 10.], [5., 10.]])
original = train.copy()
validation = np.array([[7., 12.]])
validation_original = validation.copy()
mean, scale = fit_standardizer(train)
np.testing.assert_allclose(mean, [3., 10.], rtol=0, atol=1e-10)
np.testing.assert_allclose(scale, [np.sqrt(8 / 3), 1.], rtol=0, atol=1e-10)
np.testing.assert_allclose(
    standardize(validation, mean, scale),
    [[np.sqrt(6), 2.]], rtol=0, atol=1e-10,
)
np.testing.assert_array_equal(train, original)
np.testing.assert_array_equal(validation, validation_original)
```

Also check the stated errors and repeat the validation row alongside `[99, 100]`. Its output and the fitted statistics must remain unchanged. These checks catch sample-standard-deviation scaling, validation-data leakage, input mutation, and missing input checks. They do not establish correctness for every possible matrix.

**Assumptions and open questions.** The caller supplies training rows only to fitting and keeps columns in the same order. Those are caller responsibilities. The functions can check column counts, but they cannot identify mislabeled rows or reordered features. Missing values raise an error for this increment; choosing an imputation method belongs to later work.

**Implementation constraints.** Use NumPy and the two function interfaces above so the code fits the experiment's array pipeline. Internal organization is open.

## Revise from what you learn

Trying the artifact may reveal that you wanted different behavior. Distinguish an omitted requirement, a requirement discovered during use, and a failure to meet a stated requirement. Decide whether to revise the spec or fix the code. Update the acceptance checks to match that decision. Keep the spec readable as the current agreement and preserve the reasoning in the work record and git history.

For more practice, read 6.102's [Specifications](https://web.mit.edu/6.102/www/sp26/classes/04-specifications/) and [Designing Specifications](https://web.mit.edu/6.102/www/sp26/classes/05-designing-specs/).
