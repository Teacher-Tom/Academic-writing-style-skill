# Sentence and Paragraph Patterns

All example prose below is original. Adapt it to the actual method, evidence, and terminology rather than reproducing it sentence by sentence.

## Choose a Structure by Sentence Function

| Function | Possible structure | Example |
|---|---|---|
| State a design | We introduce/design ... | We introduce a gated recurrent memory for long-horizon control. |
| Define an operation | Module + verb + object | The encoder maps observations and instructions to contextualized features. |
| Explain a purpose | To achieve X, we perform Y. | To preserve recent visual detail, we update the short-term state more frequently. |
| Explain a mechanism | Operation followed by its role | The gate merges incoming evidence with the previous state to update the memory. |
| Add a direct product | Module + operation, producing Y. | The encoder integrates observations and actions, producing a compact representation of task history. |
| Connect benefit and cost | While X preserves A, it discards B. | While a sliding window preserves recent detail, it discards evidence outside the window. |
| Explain a consequence through an operation | Doing X requires Y / increases Z. | Storing each frame separately increases memory usage as the history grows. |
| Specify time or conditions | When/Every/At ..., operation | At each consolidation step, the long-term state incorporates the short-term memory. |
| Describe a training setting | Object + passive construction | The policy is trained to predict action sequences over a longer horizon. |
| Report a result | In setting X, method changes metric Y relative to baseline Z. | Supply the actual setting, metric, and baseline before stating a comparison; do not invent a result to complete the example. |

Sentences can begin with authors, modules, inputs, or states. Choose the subject by narrative focus rather than repeatedly beginning with We or This.

Put the operation or judgment the reader should remember in the main clause, then add inputs, conditions, and products. Participial clauses suit direct results of the same operation. Use a full clause or a new sentence when a consequence introduces another subject, an additional assumption, or an independent claim.

## Relationships Within and Between Sentences

Choose expressions by the actual relationship so the reader understands why the argument moves to another method, limitation, or design:

| Relationship | Possible expressions | When useful |
|---|---|---|
| Purpose | To retain / To reduce / To enable | The next operation responds to an information need or computational constraint established earlier. |
| Concession | While / Although / Despite | The same technical choice provides a capability and incurs a cost; both clauses concern that tradeoff. |
| Alternative | instead / alternatively | Another route addresses the same problem; identify what changes in the processing strategy. |
| Contrast | However / Yet | The discussion moves from an established capability to an unresolved problem. |
| Progression | Moreover / Furthermore / More fundamentally | Add supporting reasoning; reserve More fundamentally for a deeper mechanism or assumption. |
| Consequence | therefore / thus / Consequently / As a result | The preceding text explains the mechanism producing the consequence. A connector does not supply missing causal reasoning. |
| Mechanism or detail | Specifically / By / through | Develop a general claim into concrete operations and information flow. |

Embed relationships in purpose, concession, condition, or result clauses, or mark them between sentences. Splitting everything into short sentences can obscure relationships; adding connectors cannot repair topic jumps or missing causal steps. Identify the relationship before choosing the syntax.

> While a sliding window preserves recent visual detail, it discards evidence outside the window. To retain earlier events, the memory module integrates incoming observations with its previous state. The policy then reads the updated state to condition action prediction.

This example connects a technical tradeoff, a design purpose, and an information flow. The actual architecture and retention claims must follow the current system and its evidence.

## Information Continuity

Reuse objects deliberately so the output of one operation remains traceable in the next:

> A task-conditioned encoder processes visual observations and executed actions. A Q-Former compresses the resulting features into candidate memory tokens. Gated updates merge these candidates with the previous state. The policy reads the updated memory to predict actions.

The reading order is input, features, candidate representation, state, and action. For asynchronous systems, describe reading the latest available state and accurately specify the timing of commits and reads.

Distinguish objects before reusing terms. For example, history denotes the source history, memory state the recurrent state, memory tokens its vector representation, and memory encoder the computational module. These terms are related but are not interchangeable synonyms.

## Organize Paragraphs by Function

### Problem or Limitation

A useful progression is claim, concrete situation or mechanism, task consequence, and design need. Include the steps that establish the reasoning; do not force a four-sentence template.

> A short observation window loses evidence once it leaves the context. In a search task, a previously explored route may then become indistinguishable from an unvisited one. The policy needs a compact state that preserves exploration progress.

Examples explain information needs. Experimental conclusions still require the current paper's data.

### Method Overview

State what changes before describing inputs, central operations, state flow, and outputs. An introduction needs enough detail to explain the design; place hyperparameters, full equations, and training schedules in the appropriate method sections.

> The memory module maintains a fixed-size recurrent state. An encoder compresses new observations and actions into candidate tokens, which gated updates integrate with the previous state. The action policy reads the latest available memory while the encoder processes incoming observations.

For a method with two timescales, explain how the long-term state receives the short-term state rather than merely naming both memories.

### Related Work

Compare representations, information sources, update mechanisms, and cost in relation to the current problem. Ground each comparison in the cited paper and its actual setting. Close the discussion by identifying the capability the current problem requires.

### Results

Organize around the question answered, the key comparison, and the scope or interpretation of the result. Keep conclusions close to their figure or table evidence. Distinguish component ablations, overall gains, and causal explanations.

### Contributions

Use parallel openings, such as We introduce ... throughout, or noun phrases throughout. Identify a distinct mechanism, supervision source, or capability in each item rather than repeatedly restating improved performance.

## Verbs and Claim Strength

Match verbs to objects while preserving the differences between operations:

| Operation | Useful collocations | Meaning |
|---|---|---|
| Encoding | encode observations / instructions into features | Transform inputs into representations. |
| Integration | integrate observations and actions | Combine inputs or incoming and previous information. |
| Historical consolidation | consolidate observations into a memory state | Organize distributed historical evidence into a maintained representation. |
| Compression | compress features / history into fewer tokens | Reduce the representation budget; explain information retention through training objectives and evaluation. |
| Retention | retain events / preserve visual evidence | Name the information being preserved. |
| Updating and retrieval | update a state / retrieve entries | Distinguish changing a state from reading stored entries. |
| Conditioning and alignment | condition action prediction on memory / align trajectories | Distinguish what conditions a policy from what a training objective aligns. |
| Optimization and results | optimize an objective / reduce a measured error / improve a named metric | Distinguish objectives, measured changes, and evaluation metrics. |

Check how directly the evidence supports the verb:

- **Implementation:** State confirmed operations such as gating, projection, and asynchronous scheduling directly.
- **Training objective:** Use is trained to retain ... or receives supervision for ... to identify an intended learning target.
- **Observation:** Support retains ... and improves ... with the corresponding evaluation.
- **Interpretation:** Use wording such as suggests ... when a mechanism is an explanation rather than a directly established result.

Modifiers should also have distinct roles. Compact describes representation size, recurrent the update mechanism, task-conditioned the conditioning source, and fixed-budget the capacity constraint. Tie higher-level to an actual abstraction, such as event relationships, state changes, or task progress in the relevant setting. Explain what information it organizes rather than using it as a standalone evaluation of capability.

## Revisions That Can Change Technical Meaning

| Draft claim | Editorial decision |
|---|---|
| Asynchronous execution adds no latency. | Separate execution overlap from measured critical-path overhead. Report zero added latency only when supported by the relevant measurement. |
| SFT applies the same penalty to different trajectory errors. | Check the objective. If the source only establishes the absence of a trajectory-level objective, say that token-level supervision does not directly optimize trajectory error. |
| Compression loses no information. | Distinguish a formal lossless guarantee, preservation of a particular task metric, and the information the training objective aims to retain. |
| Performance improves by a percentage. | Specify relative percent change or absolute percentage points and retain the baseline. |
| Performance improves significantly. | Check statistical significance or measured effect size and choose wording that matches the evidence. |

## Restraint in Wording

- Remove dispensable metadiscourse, such as It is important to note that ..., and repeated announcements of what the next paragraph will do.
- Preserve useful connectors: However marks a limitation, Specifically introduces an operation, and Consequently states an established consequence. Use direct information continuity when the relationship is already clear.
- Replace empty self-evaluation with verified technical properties such as recurrent, task-conditioned, and fixed-size.
- Judge necessary qualifications, real comparisons, established technical terms, and long sentences in context. Do not impose absolute word bans, fixed sentence lengths, uniform paragraph counts, or punctuation quotas.
