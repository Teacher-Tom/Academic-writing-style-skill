# Paper Figures: Purpose, Layout, and Evidence

Use when planning, revising, or critiquing academic figures and captions. Choose visual content from the paper's argument and available artifacts. The reading basis is the visually inspected CVPR papers in [Figure-Design Reading](cvpr-vla-examples.md#figure-design-reading); the guidance below is an editorial synthesis rather than conference policy.

## Assign a Role Before Choosing a Layout

State what a reader should understand after viewing the figure. Use this decision to select the subject, evidence, and level of detail.

| Figure role | Main question | Suitable content and layout | Detail to allocate elsewhere |
| --- | --- | --- | --- |
| Introduction: problem or design principle | What limitation motivates the work, and what changes? | Matched baseline/proposed panels using a shared task or interface; highlight the consequential difference. | Full internal architecture and exhaustive baseline taxonomy. |
| Introduction: capability teaser | What does the system enable? | A concrete input, the central idea or representation when needed, and a large, inspectable output or task outcome. | Layer counts, optimization details, and implementation branches. |
| Introduction: result summary | What principal quality or efficiency result motivates reading further? | A compact, measured comparison with explicit axes, units, workload, and comparison conditions. | Complete benchmark results and secondary metrics. |
| Method: framework overview | How do inputs become outputs? | A directed computation graph with meaningful intermediate representations, branches, interfaces, and outputs. | Routine internals that do not affect the claimed design. |
| Method: mechanism or supervision | How does the key operation or learning signal work? | A focused inset, aligned before/after representation, temporal unrolling, or annotated data-to-target example. | Unrelated components already established in the overview. |
| Experiment: quantitative evidence | How much changes, under which conditions? | Curves for trends, paired points or bars for categorical effects, distributions for variability, and tables for exact multi-metric comparisons. | Architecture decoration and repeated benchmark prose. |
| Experiment: qualitative evidence | What behavior, error, or retained evidence explains the measurements? | Aligned method-by-case grids, temporal sequences, localized crops, or input/prediction/reference panels. | Decorative sample galleries without an evaluative purpose. |

A paper can combine compatible roles or omit a separate teaser. Number, width, and location follow the argument and page layout. A comparison figure placed near the method still functions as evidence.

## Introduction Figures

Choose a recognizable task, observation, or output that makes the contribution concrete before readers know the implementation. For a design comparison, preserve the same interface across panels so that the changed dependency is visible. For a capability teaser, give the outcome enough area to inspect; a collection of tiny samples can obscure the capability it is meant to establish.

An intermediate representation belongs here when it explains the central idea, as a spectral representation does for image dynamics. Use a brief functional label and a visual example. Explain its full computation in the method figure.

For temporal tasks, show the cue, its later relevance, and the resulting decision on a short timeline. Include timestamps or an explicit time direction when the gap itself matters. Label schematic outcomes and measured examples according to their source. Numerical summaries should identify the metric and comparison conditions even when shown on the first page.

## Method Figures

**Trace the computation.** Establish a dominant reading direction and place inputs, transformations, representations, and outputs along it. Use separate lanes for parallel computation or modalities when they expose a real dependency. Route connectors so readers can follow the main path without repeatedly crossing unrelated branches.

**Allocate detail to the contribution.** Show a routine backbone as one block when that is enough to define its role. Expand the new interaction or transformation through an inset or a separate panel. Keep the overview and close-up at distinct levels of detail, connected by the same module name, symbol, or marked region.

**Show state and time explicitly.** Distinguish observations from maintained state and newly computed candidates. A recurrence arrow should connect identified states at identified times. In asynchronous or multirate systems, indicate update schedules and when new state becomes available to a downstream decision. A feedback arrow by itself does not establish timing or concurrency.

**Distinguish learning from deployment.** Attach data and supervision to the operation they train. Use labeled lanes, panels, or line styles to identify training-only components and deployment inputs. Define conventions locally; dashed lines, colors, and icons have no universal meaning. Mark frozen or trainable modules when their status affects interpretation.

**Explain supervision with an example.** For annotation or data construction, show the source observation, the transformation or labeling operation, and the resulting target. Spatial marks, text spans, timestamps, and action intervals should reveal what is supervised. Distinguish human labels, generated labels, and deterministic rules when they supply different signals. Aggregate counts or quality checks can accompany the example if those properties are part of the contribution.

## Experiment Figures

**Quantitative plots.** Select the display from the comparison: curves for budget, time, data, or horizon sweeps; grouped marks for a small set of categorical variants; scatter plots for quality-cost tradeoffs; distributions for variation. Label axes and units, identify metric direction where helpful, and explain uncertainty when shown. Keep comparable panels on consistent scales or clearly mark the difference. Bubble sizes and secondary axes require explicit encodings.

For efficiency, name the measured cost and workload: first-action latency, complete generation time, throughput, update runtime, memory use, or representation size. Pair cost with the corresponding quality. In control systems, show observation, decoding, dispatch, and execution intervals separately when they answer different questions. Align the timeline to recorded events rather than inferring speed from the architecture.

**Qualitative comparisons.** Use stable rows and columns for cases, methods, times, or outputs. Match inputs, crops, viewpoints, display ranges, and timestamps where appropriate. Include a reference or source image when it helps readers assess the prediction. Use callouts or enlarged crops for small differences while preserving enough context to locate them.

**Temporal behavior.** A filmstrip should make the initial condition, relevant intermediate event, and later outcome traceable. Distinguish generated goals from observations of actual execution. Preserve object identities across views and times. Domain-specific views such as trajectories or space-time slices can expose temporal errors more clearly than a row of nearly identical frames; define their axes and relation to the source video.

**Mechanism analysis.** Choose interventions, ablations, or synchronized measurements that test the proposed explanation. Attention and similarity heatmaps show the visualized quantity; use additional evidence for claims about causal use or retention. Specify the source and normalization of heatmaps and share a scale across compared panels when their magnitudes are being compared. Caption failure cases in terms of the observed error and tested condition.

## Visual Style and Page Layout

- Build a semantic hierarchy: the main computation or comparison is prominent, supporting examples are smaller, and secondary annotations remain subordinate. Use spacing and alignment to group related content before adding more enclosing boxes.
- Assign colors to stable roles such as modality, module family, method, state, or tracked identity. Choose a coherent scheme for the figure; the same color should not acquire conflicting meanings in a shared legend. Combine color with labels, shapes, line patterns, or markers when identity matters.
- Prefer readable text, restrained fills, clear boundaries, and sufficient contrast. Screenshots, photographs, depth maps, and heatmaps retain the detail and scale needed to inspect the result. Decorative icons or gradients are useful only when they convey information.
- Use parallel panel geometry for comparisons. A wide figure is useful for a long pipeline or matched grid; a compact plot, local mechanism, or failure case may fit one column. Choose column span by the content's readable size.
- Use short functional labels inside the figure and explain details in the caption or text. Standardize panel letters, module names, notation, arrowheads, and repeated symbol sizes across the manuscript.
- Keep text, connectors, and plots as vector elements when feasible, with raster resolution sufficient for image evidence at final size. Review the composed PDF for small labels, line collisions, clipped legends, and excessive empty space. No fixed color count, font size, or figure count follows from the sample papers.

## Captions and Prose

A useful caption identifies the subject, explains how to read the panels, states the essential conditions or encodings, and gives the supported observation. Select these elements according to the figure's purpose. A framework caption explains the computation; a result caption identifies the comparison and measured pattern. Preserve the distinction between a design goal and an empirical finding.

Original sentence patterns to adapt:

| Purpose | Possible structure |
| --- | --- |
| Introduce an overview | Overview of [framework]. Given [inputs], [module] produces [representation], which conditions [output computation]. |
| Explain a comparison | (a) [Baseline] uses [dependency]. (b) [Proposed design] introduces [operation], enabling [specified behavior]. |
| Guide panel reading | Rows correspond to [cases], and columns show [input, prediction, reference]. |
| Explain training and inference | The [labeled branch] supplies [training target]; deployment uses [available inputs and computation]. |
| Define temporal evidence | Frames show [event] at [times]; [visual encoding] identifies [predicted goals, observations, or tracked objects]. |
| Describe a trend | [Metric] is measured as [budget or horizon] varies under [conditions]. [Observed pattern] is concentrated in [range or setting]. |
| Describe a boundary | Under [tested condition], [specific output error] appears in [marked region or interval]. |

Use the surrounding paragraph to interpret the key comparison and connect it to the paper's claim. Let the figure carry the detailed visual evidence and the caption carry the reading instructions.

## Apply the Guidance

Before authoring a figure, identify its role, primary claim, source artifacts, intended comparison, and the content that must remain legible at the target width. Sketch the information hierarchy, then select panel geometry and visual encodings. Review whether each panel advances that role and whether its arrows, labels, data, and caption agree with the manuscript. Preserve editable sources and record the provenance of measured or generated outputs.
