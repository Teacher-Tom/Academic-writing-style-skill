# Manuscript Structure and Experimental Narrative

Use for outlining a paper or revising relationships among sections. Apply the relevant decisions to the requested scope; a sentence-level edit does not require reorganizing the manuscript.

## Connect Contributions to Evidence

Before selecting headings, identify each central claim, the design that supports it, and the evidence available to assess it. A compact planning aid is:

| Contribution | Method content | Evidence to consider |
|---|---|---|
| A representation or memory mechanism | Define the representation, capacity, inputs, and transformations or state updates. | Assess retained information or fidelity, then test downstream utility with controlled comparisons. |
| A learning objective | Explain its target behavior, formulation, and optimized variables. | Isolate the objective's effect and measure the behavior it is intended to change. |
| A dataset or supervision scheme | Describe sources, construction, coverage, filtering, and its training role. | Examine annotation quality, coverage, or controlled training benefit as appropriate to the claim. |
| An efficient execution strategy | Explain the deployed computation and its relationship to training. | Compare task performance and relevant runtime or memory costs under stated hardware and operating conditions. |
| A transfer capability | Define source and target distributions and any adaptation procedure. | Evaluate held-out settings and distinguish zero-shot transfer from adaptation. |

Select evidence that answers the paper's claims. An outline can propose missing analyses, but drafted results must reflect completed measurements.

## Choose the Reading Order

- Introduce an interface or representation before modules that consume it. Define the quantities needed to understand an objective before presenting the loss.
- Place related work where it gives readers the context needed for the next argument. Early related work can establish the technical landscape; later related work can compare mechanisms after the new design is understood.
- Give data construction or an evaluation protocol its own subsection when it is a contribution or necessary to interpret the results. Otherwise introduce it where the corresponding supervision or evaluation is explained.
- Give each figure or table an explanatory role. An overview can establish information flow; a schedule can clarify training stages or asynchronous execution; a comparison can isolate a capability or tradeoff. Choose what the reader needs rather than a fixed figure sequence.

## Develop the Method

Establish the task, available inputs, maintained state, outputs, and operating constraints at the level needed to understand the design. Follow with the central mechanism and the components that depend on it. Group implementation modules by the function they jointly perform.

For each substantive design, make its purpose, inputs, computation, output, and training role easy to locate. Use equations to resolve relationships that prose alone leaves ambiguous. Keep established notation consistent across the overview, equations, algorithm, and figures.

Separate how the system is learned from how it runs. Explain training stages, losses, updated or frozen parameters, and auxiliary supervision where they affect interpretation. Then specify which components execute at inference and how their outputs condition subsequent operations. In temporal systems, distinguish observation, state-update, prediction, and execution schedules.

Present dataset construction alongside the learning need it serves. Keep enough detail in the main text to explain the supervision; use supplementary material for full annotation instructions, conversion procedures, or inventories when those details are not themselves central to the contribution.

For local mechanism explanations, equation/prose relationships, and optimization descriptions, read [method-writing.md](method-writing.md).

## Build the Experimental Narrative

Choose an order that establishes the central result and then explains it. Useful evidence includes overall task performance, representation or intermediate capability, component effects, generalization, efficiency, and observed failure cases. Their order depends on the paper: an unfamiliar capability may benefit from an early qualitative demonstration, while a policy paper may lead with closed-loop results.

- Supply the setup needed to interpret the first comparison: evaluation settings, metrics, baselines, relevant data splits, and adaptation or resource conditions.
- Relate subsections to research claims. Benchmark names can identify settings within a comparison; explain the distinct question each comparison addresses.
- For representation contributions, assess the representation itself and its downstream use. Separate those measurements, then connect them through ablations, controlled interventions, or informative examples.
- Make ablations isolate the claimed change. Account for training data, model capacity, optimization budget, and operating conditions when they could explain the difference.
- Pair efficiency with quality. State the compression denominator, retained capacity, runtime quantity, hardware, and comparison protocol needed to interpret the claim. In control systems, observation and execution rates can also affect performance.
- Give qualitative examples an analytical purpose, such as showing evidence retention, a state transition, recovery, or an observed failure. Match the explanation to what the example establishes.
- In the accompanying prose, identify the finding, comparison, and implication. Select the numbers needed for that reasoning instead of narrating every table entry.

For experimental prose, controlled-comparison descriptions, quantities, and reporting templates, read [experiment-writing.md](experiment-writing.md).

## Divide Main Text, Discussion, and Supplement

Keep central definitions, mechanism equations, essential training logic, and decisive evidence in the main text. Place exhaustive hyperparameters, extended task descriptions, additional comparisons, and implementation procedures in supplementary material when readers can assess the contribution without them.

Use a discussion section when interpretation, cost, or observed limitations require sustained treatment. A short conclusion can instead connect the findings to the central problem and state material boundaries. Keep new methods and unreported results in their appropriate sections.

For concrete variations in section order and evidence organization, see [the whole-paper reading examples](cvpr-vla-examples.md#whole-paper-organization-reading).
