# Development and review process

## One complete learning unit at a time

The course is organised in modules, but a bounded learning unit is the object of drafting and review. The first draft should be usable on its own, with necessary prerequisite reminders and references to previously established results. A module does not need to be written in one large response.

1. **Define the unit:** identify the main result, prerequisites, representative example, and intended depth.
2. **Prepare the complete draft:** include intuition, definitions, assumptions, mathematical argument, examples, proposed computation, exercises, and worked solutions.
3. **Check before author review:** verify sources and nontrivial mathematical steps. Execute included computational examples when an executable notebook is part of the draft. Mark unresolved steps and unexecuted code explicitly.
4. **Author review:** incorporate questions and comments. Repair the main explanation when the missing detail is needed to follow it; put optional extensions in supplementary notes.
5. **Mathematical and computational audit:** revisit the argument with its stated assumptions, inspect failure cases, and check the implementation independently of the narrative where possible.
6. **Prepare release:** render the text, execute the notebook from a clean state, check references and figures, and record the review status.

Teaching explanations, derivations, and prediction exercises are optional tools for improving understanding. They do not gate access to a complete lesson or its solutions.

## Standard unit components

- Main question, objectives, and prerequisites.
- Intuition and precise definitions, with notation introduced before use.
- Foundational result with all essential assumptions.
- Worked derivation or proof, with nontrivial steps explained.
- Advanced details, counterexamples, and relevant extensions.
- Independent-data and time-series connections, clearly distinguishing illustrations from established extensions.
- Python experiment: purpose, data-generating process, assumptions, code, output, and interpretation.
- Conceptual questions, exercises, and worked solutions.
- Checked references and useful supplementary notes.

## Mathematical review

For each substantive result, record the source and edition when applicable, which assumptions are used, whether the argument has been reconstructed, and any unresolved step. Distinguish sufficient conditions from necessary conditions; pointwise from uniform results; marginal from joint convergence; and probability limits from moment or sample-path claims.

A reviewer may miss an error. “Reviewed” records a completed review process, not formal certification. Agreement between model outputs is not a substitute for checking the argument and its source.

## Computational review

- Make the simulated model and target agree with the theory.
- Treat deliberately violated assumptions as separate, labelled experiments.
- Record environment requirements, random-number generation, sample sizes, and replication counts.
- Compare against simple analytic quantities or independently implemented special cases when available.
- Report relevant Monte Carlo uncertainty, including the distinction between simulation replications and bootstrap draws.
- Explain initialization and sampling for time-series examples.
- Distinguish evidence about finite-sample behaviour from an asymptotic proof.

Do not report numerical results before the corresponding code has run. Re-running code successfully does not establish mathematical validity.

## Two progress records

[STATUS.md](STATUS.md) is the public record of material availability. It contains no personal assessment of the author's understanding.

Keep the personal learning log in the ChatGPT project or another private author workspace. It records questions, explanations the author can give independently, derivations that need revisiting, and next steps. Learning progress and publication progress are updated separately.

## Status definitions

- **Planned:** a unit is in the roadmap; substantive teaching material is not yet available.
- **Draft:** substantive text or code exists; the audit is incomplete or has open issues.
- **Reviewed:** the mathematical, computational, and presentation checks applicable to the unit have been recorded.
- **Released:** the reviewed version is publicly accessible with its supporting files and reproducibility instructions.

## Book and repository workflow

Use Quarto files as the canonical book text and notebooks as executable reader experiments. Share computation through reusable Python functions or embedded notebook output where practical, so the book and notebook do not maintain conflicting versions of the same result.

Create a minimal Quarto scaffold with the pilot. Add actual chapters, notebooks, supplementary notes, and shared code as they exist. The current package does not include a working Quarto site or executed teaching notebooks.

Before publishing a substantive unit, check its rendered mathematics, cross-references, figures, and links. Link to a clear sample unit from the README when one is available. Present the roadmap as planned coverage and describe completed content accurately.

