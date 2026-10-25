# Asymptotic Econometrics with Python

## Revised course structure

Author and editor: Ali Habibnia  
Revision: 2, 24 October 2026  
Status: provisional curriculum; teaching units have not yet been drafted.

## Purpose and audience

Develop a rigorous, readable account of asymptotic econometrics with reproducible Python experiments. The intended readers are graduate students, researchers, and quantitatively trained practitioners familiar with basic probability, calculus, linear algebra, and regression. Targeted reminders and reference appendices will support readers who need to refresh these tools.

The course covers independent observations, beginning with the i.i.d. baseline, and time series. Time-series examples appear from the opening units. General dependent-data results are established only after their prerequisites have been developed. DML and separate manuscript projects remain outside the present scope.

## How to use this structure

The original 26-topic inventory is retained through 13 provisional core modules, six advanced extensions, and supporting notes. Modules organise related material; their numbered learning units are the manageable objects drafted and reviewed one at a time. These groupings do not make the underlying subject shorter. They provide useful stopping points and allow the book's eventual chapter boundaries to emerge from actual teaching material.

There are 49 suggested core units. This is a working inventory, not a fixed set of assignments or a completion timetable. Unit boundaries will be reassessed after the first two or three units. Quality and understanding govern progress.

Each unit has two treatments:

- **Foundational:** intuition, definitions, all assumptions needed for the stated result, a worked argument, an econometric example, and a computational illustration where useful.
- **Advanced:** fuller proofs, technical lemmas, remainder bounds, alternative conditions, counterexamples, and extensions. Any changed theorem must carry its own assumptions.

A foundational treatment must not hide essential restrictions in an advanced section.

## Core sequence at a glance

| Module | Theme | Suggested units |
| --- | --- | ---: |
| M01 | Convergence, stochastic orders, and rates | 3 |
| M02 | Laws of large numbers and sample moments | 3 |
| M03 | Central limit theorems and normal approximation | 4 |
| M04 | Mapping results, studentization, and delta methods | 3 |
| M05 | Dependence structures for time series | 4 |
| M06 | Dependent-data limit theorems and long-run variance | 4 |
| M07 | Identification, uniform convergence, and consistency | 4 |
| M08 | OLS and dynamic regression as complete examples | 4 |
| M09 | M-estimation, Z-estimation, and nonlinear least squares | 4 |
| M10 | Likelihood, quasi-likelihood, and misspecification | 4 |
| M11 | Instrumental variables and GMM | 4 |
| M12 | Confidence intervals, hypothesis tests, and local power | 4 |
| M13 | Bootstrap methods for independent and dependent data | 4 |

## Preparation alongside the first units

Use brief prerequisite reminders at the point of need. Develop the following supporting notes progressively rather than requiring a large preliminary course:

- **P01 — Probability and notation:** random variables and vectors, events, distributions, expectation, conditional expectation, and integrability.
- **P02 — Analysis and linear algebra:** norms, eigenvalues, continuity, compactness, derivatives, Taylor expansions, and useful matrix identities.
- **P03 — Proof tools:** quantifiers, inequalities, epsilon arguments, bounding remainders, and identifying the exact theorem being applied.
- **C01 — Python and Monte Carlo practice:** environment setup, random-number generators, independent replications, numerical diagnostics, simulation uncertainty, and interpretation of figures.

The Python companion begins with the first notebook. Coverage, size, and bootstrap-specific Monte Carlo measures are added when those concepts enter the course.

## I. Core probability tools

### M01 — Convergence, stochastic orders, and rates

**Prerequisites:** Targeted probability and notation notes; no earlier module.

**Learning units**

1. **M01.1: Random sequences and convergence in probability.** Define the objects that converge, use sample averages as the running example, and give an epsilon–probability argument.
2. **M01.2: Distributional, almost-sure, and Lp convergence.** Distinguish convergence of distributions, sample paths, and moments; establish implications under stated conditions and examine counterexamples.
3. **M01.3: Stochastic orders and rates.** Develop O_p and o_p, their algebra, normalizations, and the interpretation of a negligible remainder.

**Independent-data example:** Independent sample averages and simple random-sequence examples.

**Time-series connection:** A stationary autoregressive sample-average illustration, explicitly labelled as a preview until M05–M06 establish the conditions.

**Planned notebook:** Separate a single trajectory from repeated-sample distributions; compare sample-average behaviour under independence and persistence.

**Understanding objective:** Identify the appropriate convergence statement and manipulate a simple stochastic remainder.

### M02 — Laws of large numbers and sample moments

**Prerequisites:** M01.

**Learning units**

1. **M02.1: Weak laws and proof strategies.** Study sufficient conditions for averaging, including a finite-variance proof and the distinction between integrability and stronger moment assumptions.
2. **M02.2: Strong laws and sample-moment consistency.** Develop almost-sure convergence and applications to sample moments under explicit conditions.
3. **M02.3: When averaging fails.** Examine failures of moment or dependence conditions; distinguish a theorem's inapplicability from a demonstrated failure of its conclusion.

**Independent-data example:** Means and sample moments with finite moments, together with an infinite-mean counterexample.

**Time-series connection:** Compare dependent sample averages experimentally; explain why a stationary process needs further conditions for convergence to an unconditional mean.

**Planned notebook:** Vary distributional tails and dependence while recording the sampling variability of averages.

**Understanding objective:** Choose a suitable LLN and state exactly what it establishes for a sample moment.

### M03 — Central limit theorems and normal approximation

**Prerequisites:** M01–M02.

**Learning units**

1. **M03.1: The i.i.d. central limit theorem.** Derive the normalization and limiting variance, and distinguish an asymptotic distribution from an exact finite-sample distribution.
2. **M03.2: Vector limits.** Develop joint convergence and multivariate normal approximation, including the role of the Cramér–Wold device.
3. **M03.3: Beyond identical distributions.** Introduce triangular arrays and independent non-identically distributed observations; reserve full Lindeberg and Lyapunov arguments for the advanced treatment.
4. **M03.4: Accuracy and failure of approximation.** Investigate skewness, tail behaviour, and sample size; keep finite-sample diagnostics separate from proof.

**Independent-data example:** Scalar and vector sample means.

**Time-series connection:** Show how dependence changes the variance of an average; defer the general dependent-data CLT to M06.

**Planned notebook:** Compare standardized sampling distributions across sample sizes and tail conditions.

**Understanding objective:** Justify a normalization and limiting covariance under an appropriate CLT.

### M04 — Mapping results, studentization, and delta methods

**Prerequisites:** M01 and M03.

**Learning units**

1. **M04.1: Continuous mapping and Slutsky.** Work with joint limits and continuous transformations; identify when marginal convergence is insufficient.
2. **M04.2: First-order delta methods and studentization.** Develop scalar and vector derivatives, estimated scaling, and remainder bounds.
3. **M04.3: Higher-order and degenerate cases.** Study vanishing first derivatives and the resulting changes in normalization and limit law.

**Independent-data example:** Transformations and ratios of sample moments.

**Time-series connection:** Apply the same mapping tools conditional on a valid dependent-data limit, revisiting the example after M06.

**Planned notebook:** Compare regular and zero-derivative transformations with their corresponding normalizations.

**Understanding objective:** Derive the limit of a transformed estimator and check that the expansion remainder is negligible.

## II. Time-series foundations

### M05 — Dependence structures for time series

**Prerequisites:** M01–M02; conditional-expectation refresher as needed.

**Learning units**

1. **M05.1: Stationarity and linear processes.** Distinguish strict and covariance stationarity; study stable autoregressions, linear representations, and initialization.
2. **M05.2: Ergodicity and time averages.** Explain the extra role of ergodicity and the conditions under which time averages recover population quantities.
3. **M05.3: Filtrations and martingale differences.** Define the information set and conditional-mean restrictions; distinguish lack of correlation from independence.
4. **M05.4: Mixing and alternative dependence conditions.** Introduce mixing concepts and how moment and dependence conditions enter limit theorems.

**Independent-data example:** Independence as a reference case.

**Time-series connection:** Stable AR processes and selected martingale-difference or nonlinear examples.

**Planned notebook:** Compare covariance patterns, conditional-mean behaviour, and time averages across carefully specified processes.

**Understanding objective:** State a dependence model precisely and avoid treating stationarity, ergodicity, and mixing as interchangeable.

### M06 — Dependent-data limit theorems and long-run variance

**Prerequisites:** M03–M05.

**Learning units**

1. **M06.1: Laws of large numbers under dependence.** Develop ergodic and selected martingale or mixing routes, with their respective assumptions.
2. **M06.2: Central limit theorems under dependence.** Work through selected martingale and mixing results; identify the moment, variance, and dependence restrictions.
3. **M06.3: Long-run variance and its estimation.** Connect autocovariance sums and the spectral interpretation; introduce HAC kernels and bandwidth choices.
4. **M06.4: Studentization with dependence.** Combine a valid CLT and consistent variance estimator, and assess finite-sample sensitivity.

**Independent-data example:** Recover the independent-data variance as an appropriate special case.

**Time-series connection:** Stationary sample averages and score or moment sequences.

**Planned notebook:** Compare empirical variance, analytic variance where available, and naive or HAC interval coverage.

**Understanding objective:** Connect a dependence assumption to a valid limit theorem and matching variance estimator.

## III. Estimation

### M07 — Identification, uniform convergence, and consistency

**Prerequisites:** M01–M02 and M04; M05–M06 for dependent-data applications.

**Learning units**

1. **M07.1: Population targets and identification.** Define the estimand and population criterion or moment restrictions; explain separation and the role of the parameter space.
2. **M07.2: From pointwise to uniform convergence.** Show why pointwise convergence may be insufficient; develop useful uniform-law conditions.
3. **M07.3: Consistency of extremum estimators.** Apply an argmax or argmin argument and trace each assumption.
4. **M07.4: Approximate optimization and boundary issues.** Allow numerical approximation where justified and identify limitations of compactness or interior assumptions.

**Independent-data example:** A simple extremum estimator with an identified target.

**Time-series connection:** The same type of objective under an appropriate dependent-data uniform law.

**Planned notebook:** Examine empirical objective functions, optimizer behaviour, and identification strength.

**Understanding objective:** Build a consistency proof from identification, uniform convergence, and an optimization argument.

### M08 — OLS and dynamic regression as complete examples

**Prerequisites:** M06–M07 and the linear-algebra refresher.

**Learning units**

1. **M08.1: Consistency of OLS.** Separate exogeneity, rank, and moment requirements; derive the probability limit.
2. **M08.2: Asymptotic linearity and variance.** Obtain the expansion and limiting covariance; compare homoskedastic and heteroskedastic formulations.
3. **M08.3: Lagged regressors and stable autoregressions.** State the relevant orthogonality and dependence conditions for dynamic regressions.
4. **M08.4: Feasible inference.** Match conventional, heteroskedasticity-robust, or HAC covariance estimation to the sampling assumptions.

**Independent-data example:** Linear regression with homoskedastic or heteroskedastic errors.

**Time-series connection:** Stable autoregressive and dynamic-regression examples; endogeneity introduced separately as an explicit violation.

**Planned notebook:** Compare bias, empirical variance, estimated standard errors, and coverage under the stated designs.

**Understanding objective:** Explain a complete consistency-and-normality argument and select a justified covariance estimator.

### M09 — M-estimation, Z-estimation, and nonlinear least squares

**Prerequisites:** M04 and M06–M08; multivariate differentiation as needed.

**Learning units**

1. **M09.1: General criteria and estimating equations.** Define M- and Z-estimators, their targets, and local identifying conditions.
2. **M09.2: Local expansions and remainders.** Work through derivative or Jacobian convergence, invertibility, and asymptotic linear representations.
3. **M09.3: Nonlinear least squares.** Use a concrete nonlinear regression to connect the generic result to an implementation.
4. **M09.4: Sandwich covariance under different sampling schemes.** Separate the sensitivity matrix from the covariance or long-run covariance of the estimating functions.

**Independent-data example:** A smooth nonlinear regression or estimating-equation problem.

**Time-series connection:** A selected stationary nonlinear time-series example under verified conditions.

**Planned notebook:** Align the implemented objective, derivatives, estimator, and covariance formula; assess optimization sensitivity.

**Understanding objective:** Use a general estimation theorem without hiding model-specific identification or remainder conditions.

### M10 — Likelihood, quasi-likelihood, and misspecification

**Prerequisites:** M09.

**Learning units**

1. **M10.1: Scores, Hessians, and regularity.** Define the likelihood or conditional likelihood, parameter space, and differentiation assumptions.
2. **M10.2: Consistency and asymptotic normality.** Develop the estimator's limit under explicit identification and sampling conditions.
3. **M10.3: Information equality and efficiency.** Explain when information identities and standard efficiency claims apply.
4. **M10.4: Quasi-likelihood and pseudo-true targets.** Study misspecification, sandwich covariance, and selected dependent-data applications.

**Independent-data example:** A correctly specified likelihood followed by a controlled misspecification.

**Time-series connection:** A simple conditional Gaussian model, with the score process and relevant dependence assumptions identified.

**Planned notebook:** Compare model-based and sandwich uncertainty when the working distribution is changed.

**Understanding objective:** Distinguish a correctly specified likelihood result from a quasi-likelihood result.

### M11 — Instrumental variables and GMM

**Prerequisites:** M06–M09; M10 is useful but not required.

**Learning units**

1. **M11.1: Moment restrictions and identification.** State instrument validity, relevance, and rank conditions; separate identification from estimation.
2. **M11.2: IV and two-stage least squares.** Derive the estimator and connect its asymptotic representation to a moment equation.
3. **M11.3: GMM weighting and variance.** Study one-step and two-step weighting under independent or dependent observations.
4. **M11.4: Overidentifying restrictions.** Develop the test under its stated conditions and preview the limits of regular approximations with weak identification.

**Independent-data example:** A controlled endogeneity-and-instruments design.

**Time-series connection:** Moment restrictions with serially dependent moment sequences and appropriate long-run covariance estimation.

**Planned notebook:** Compare estimators and weighting choices while holding the target and data-generating process fixed.

**Understanding objective:** Derive a GMM limit and explain the separate roles of validity, relevance, weighting, and variance estimation.

## IV. Inference and resampling

### M12 — Confidence intervals, hypothesis tests, and local power

**Prerequisites:** M04, M06, and M09; M10–M11 for the corresponding examples.

**Learning units**

1. **M12.1: Confidence intervals and test inversion.** Construct inference from a valid limit and variance estimator; discuss studentization.
2. **M12.2: Wald, score, and likelihood-ratio arguments.** Establish each result under its own conditions; address nonlinear restrictions.
3. **M12.3: Size, power, and local alternatives.** Distinguish pointwise asymptotic statements, finite-sample performance, and local-power calculations.
4. **M12.4: Inference with dependence or misspecification.** Connect the chosen test and correction to the estimated model and sampling scheme.

**Independent-data example:** Mean, regression, and selected likelihood or moment restrictions.

**Time-series connection:** Comparable restrictions using appropriate dependent-data covariance or likelihood conditions.

**Planned notebook:** Report coverage, rejection frequencies, and their Monte Carlo uncertainty across designs.

**Understanding objective:** Match an inferential procedure to its assumptions and interpret a simulation-based size or power comparison.

### M13 — Bootstrap methods for independent and dependent data

**Prerequisites:** M12; relevant estimator modules.

**Learning units**

1. **M13.1: What bootstrap consistency means.** Define the conditional approximation being sought and distinguish implementation from validity.
2. **M13.2: Independent-data bootstrap inference.** Study selected percentile and studentized methods and regularity conditions.
3. **M13.3: Block and stationary bootstrap methods.** Preserve relevant dependence, state assumptions, and examine block-length choices.
4. **M13.4: Selected sieve methods and failure cases.** Use a clearly justified model class; examine tuning and nonregular cases where a standard bootstrap argument fails.

**Independent-data example:** Regular sample-mean or regression statistics.

**Time-series connection:** Stationary sample averages or autoregressive examples with justified resampling schemes.

**Planned notebook:** Compare analytic and resampling-based inference, separating outer simulation replications from inner bootstrap draws.

**Understanding objective:** Explain the target bootstrap approximation and choose a resampling design consistent with the data structure.

## Advanced extensions

These preserve the later topics in the original outline. They are selected after the relevant core material is understood and reviewed. Their titles are provisional and do not create a publication deadline.

### A01 — Weak convergence of stochastic processes

**Prerequisites:** M06.

- Function spaces, tightness, and process-level convergence.
- Brownian motion and functional CLTs.
- Continuous transformations of partial-sum processes.

**Planned experiment or proof exercise:** Compare scalar and process-level diagnostics for partial sums.

### A02 — Empirical processes and stochastic equicontinuity

**Prerequisites:** M07–M09; A01.

- Empirical distributions and uniform laws.
- Glivenko–Cantelli and Donsker concepts.
- Random-index arguments and stochastic equicontinuity.

**Planned experiment or proof exercise:** Study uniform deviations and reconstruct a concrete random-index proof step.

### A03 — Quantiles, nonsmooth statistics, and statistical functionals

**Prerequisites:** M09; relevant A02 material.

- Quantile representations and nonsmooth estimating equations.
- Influence representations and functionals.
- Functional delta methods and regularity failures.

**Planned experiment or proof exercise:** Compare regular and irregular quantile problems under explicitly stated distributional conditions.

### A04 — Nonparametric estimation and inference

**Prerequisites:** M07–M09; selected A02 material for uniform inference.

- Kernel and series estimators.
- Bias, variance, rates, and tuning.
- Pointwise versus uniform inference and the role of smoothing bias.

**Planned experiment or proof exercise:** Connect tuning choices to estimation error and coverage.

### A05 — Unit roots and near-unit-root asymptotics

**Prerequisites:** M08; A01.

- Stationary, unit-root, and local-to-unity sequences.
- Changing normalizations and Brownian-functional limits.
- Consequences for regression and inference.

**Planned experiment or proof exercise:** Compare stationary, highly persistent, and unit-root autoregressions without treating them as the same asymptotic regime.

### A06 — Selected failures of regular asymptotics

**Prerequisites:** M03 for heavy tails, M10 for boundary likelihood cases, M11 for weak identification.

- Boundary-parameter case study.
- Weak-identification case study.
- Heavy-tail case study with alternative rates or limits.

**Planned experiment or proof exercise:** Identify the failed assumption before evaluating a replacement approximation.

## Recurring examples and cross-references

1. Sample averages connect convergence, laws of large numbers, CLTs, delta methods, long-run variance, confidence intervals, and bootstrap approximations.
2. Linear regression connects identification, consistency, asymptotic linearity, covariance estimation, and tests.
3. A stable autoregression supplies an early dependence illustration and later a complete dynamic-estimation example.
4. A smooth nonlinear regression illustrates general M- and Z-estimation results and their model-specific requirements.
5. Moment restrictions connect IV, GMM, weighting, identification, and inference.

At every revisit, state what is inherited from an earlier result and what new assumption is required. Early dependent-data illustrations must be labelled as previews when their proof has not yet been developed. Simulation cannot establish an almost-sure limit or validate a theorem by itself.

## First production cycle

**Pilot:** M01.1, “Random sequences and convergence in probability.”

Prepare a complete first draft of that bounded unit: intuition, formal definition, a transparent worked argument, an independent-sample example, an explicitly qualified time-series illustration, an executed notebook, and exercises with solutions. Include only the prerequisite notes needed for this unit.

The author reads the draft and raises questions. Revise the main text wherever a clarification is necessary to understand the result; use supplementary notes for genuine extensions. Optional teaching explanations can identify gaps without becoming prerequisites for receiving complete material.

Render the pilot in a minimal Quarto book before scaling up. Check equation display, references, figure captions, notebook links, and navigation. M01.2 and M01.3 follow after the pilot's review, with boundaries adjusted if the first unit proves too broad or too narrow.

## Evidence of progress

Public [material status](STATUS.md) records availability and review of teaching units. Personal understanding is recorded separately in the private author workspace. Producing or reading a polished file does not itself establish mastery.

For substantial units, useful evidence includes explaining the result, reconstructing a key argument, identifying a failed assumption, and interpreting or adapting the experiment. These are voluntary learning checks rather than compulsory examinations.

