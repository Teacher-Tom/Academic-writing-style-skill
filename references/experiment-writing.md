# Experiment Writing: Comparisons, Results, and Interpretation

Use for experimental sections, result paragraphs, ablations, efficiency analysis, and figure/table text. Write from the available measurements and distinguish proposed analyses from completed experiments. Choose the experimental narrative according to the claims being assessed.

## Establish the Question and Comparison

Give each substantive experiment a role in the argument: overall performance, component utility, representation quality, transfer, efficiency, or behavior under a particular condition. Explain how the selected setting and metric assess that role.

State the conditions needed to interpret a comparison, such as test splits, baseline checkpoints, training or adaptation data, resource budgets, and execution protocols. Distinguish zero-shot evaluation from fine-tuning on a held-out environment. Identify trial counts, repeated runs, aggregation, and uncertainty measures where they inform interpretation, preserving what was actually reported.

## Build a Result Paragraph Around a Finding

Connect the local question or setting, principal finding, selected numerical evidence, and its implication. Use the order that makes the result understandable. Place figure or table references beside the finding they support and select the differences or trends needed to explain it.

Specify the baseline, metric, direction, and evaluation scope. Distinguish an average gain from improvement on every setting, and identify where benefits are concentrated or results are mixed. Keep measured changes separate from explanations of their cause.

| Paragraph type | Information to emphasize |
|---|---|
| Main comparison | Baseline, evaluation setting, metric, and the principal gain or tradeoff. |
| Ablation | Changed design, controlled conditions, and the capability affected. |
| Generalization | What is held out, whether adaptation occurs, and where transfer benefits appear. |
| Efficiency | Workload, hardware, measured cost, and corresponding quality. |
| Qualitative analysis | A concrete state or behavior and the finding it helps explain. |

## Explain Ablations and Capability Analysis

State whether an ablation removes a component, replaces it with an alternative, adds a design, or varies a parameter. Identify the conditions needed to isolate that change, such as capacity, training data, optimization budget, or inference schedule. When capacity or cost is intentionally varied, describe the resulting tradeoff.

Interpret component effects within the tested configuration. Incremental additions assess gains along that sequence; claims about independent effects or interactions need comparisons that support those interpretations.

For representation contributions, distinguish intermediate quality from downstream performance. Connect them through controlled substitutions, ablations, or informative execution examples when available. Give qualitative cases an analytical role, such as evidence retention, a state transition, recovery, or failure under an observed condition.

## Report Efficiency and Quantities Precisely

Name the measured quantity: module runtime, end-to-end latency, throughput, peak memory, or representation size. State the workload, hardware, operating conditions, and quality needed to interpret it. For compression, identify the denominator and retained capacity; for speedup or relative reduction, identify the baseline.

Preserve units, aggregation, and the distinction between relative percent changes and percentage-point differences in rates. Tie words such as consistent, robust, and generalizes to the settings or variations evaluated. Use specific effect sizes where possible and distinguish statistical significance from descriptions of magnitude.

## Choose Sentences by Their Function

These are original templates. Fill them with actual conditions, comparison targets, and measurements.

| Function | Possible structure |
|---|---|
| State the question | We evaluate whether ... under ... . |
| Define the setting | We evaluate ... on ..., using ... as the primary metric. |
| Specify controls | All variants use the same ..., with ... held fixed. |
| Report a main result | Our method achieves ... on ..., compared with ... for ... . |
| Report a rate difference | Our method improves success rate by ... percentage points over ... . |
| Locate the largest gains | The gains are largest on ..., where ... . |
| Isolate a design | To isolate the effect of ..., we replace ... with ... . |
| Report an ablation | Removing ... reduces ... from ... to ... . |
| Describe a trend | As ... increases, ... remains ... / declines ... . |
| Relate cost and quality | Under the same ..., our method reduces ... while maintaining ... . |
| Interpret evidence | These results suggest that ... . |
| Describe an observed boundary | Performance degrades when ..., indicating a limitation in ... . |

## Match Words to Evidence

| Purpose | Useful words and collocations |
|---|---|
| Evaluate and measure | evaluate on/in; benchmark against; measure; report |
| Compare outcomes | outperform ... on ...; match; improve ... by ...; reduce ... from ... to ... |
| Describe an intervention | remove; replace; vary; hold fixed; isolate the effect of |
| Describe a trend | increase; decline; plateau; remain stable; degrade |
| Interpret evidence | show; indicate; suggest; support |

Use concrete metric names: improve task success rate or reduce inference latency is more informative than improve performance or reduce cost. Report observed changes directly. Choose interpretation verbs according to the evidence: show can introduce a measured pattern, support can relate evidence to a design claim, and suggest can introduce an explanation not established directly by the comparison.

## Coordinate Text, Figures, and Tables

Make the relevant metric directions, units, variant definitions, budgets, and aggregation or measurement conditions accessible in the caption, table, or nearby setup. Keep the prose focused on the finding and its meaning, while the visual supplies the detailed comparison. Describe qualitative evidence in terms of what is visible or recorded and distinguish it from inferred internal behavior.

For source-specific observations, see [the CVPR experiment reading](cvpr-vla-examples.md#experiment-writing-reading). For choosing the overall evidence order, see [manuscript-structure.md](manuscript-structure.md).
