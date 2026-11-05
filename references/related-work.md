# Related Work: Organization, Comparison, and Language

Use for drafting or revising related work and literature-positioning passages. Choose comparison axes from the paper's central problem and actual contributions. For source-specific examples, see [the CVPR related-work reading](cvpr-vla-examples.md#related-work-reading).

## Select Comparison Axes

Group methods by the technical choices relevant to the current argument, such as representation, information source, temporal coverage, update mechanism, training signal, or computational dependency. Use chronology to explain how a route developed when that history matters.

Define categories through their mechanisms and acknowledge overlap when needed. A method can combine selection, aggregation, learned prediction, or retrieval. Expand on the closest methods where their differences determine the current work's positioning; use grouped citations for a shared operation or assumption.

## Build a Paragraph Around a Technical Route

A useful progression is route overview, representative mechanisms, capability and cost, and the current work's relationship. Include the moves needed for the argument, without imposing a sentence count or requiring every paragraph to end in criticism.

Open with the route's goal or distinguishing operation. Introduce representative methods to substantiate or refine that shared description. Compare them on the same axis so a shift in representation, supervision, or execution remains traceable across sentences.

Explain a limitation through the design producing it and its consequence for the target task. Distinguish a dependence, a capacity restriction, a runtime cost, and an observed performance limitation. State the relevant population and conditions; absence of an explicit objective alone does not establish inability.

Position the current work through the actual relationship: extending a formulation, changing an input or state update, transferring an idea to another setting, or providing a complementary capability. Keep that positioning focused on the comparison at hand.

## Choose Sentences by Their Function

The following are original templates. Fill them with verified mechanisms and claims; select syntax according to the relationship being expressed.

| Function | Possible structure |
|---|---|
| Introduce a route | A line of work addresses ... by ... . |
| State the classification axis | Approaches differ in whether ... or ... . |
| Identify representatives | Representative methods include A and B, which ... . |
| Compare on a shared axis | A predicts ... from ..., whereas B learns ... through ... . |
| Describe development | Building on ..., subsequent work extends ... to ... . |
| Connect capability and cost | While ... enables ..., it requires ... . |
| Explain a consequence | Relying on ... increases ..., limiting ... . |
| Identify the nearest work | Most relevant to our work are methods that ... . |
| State inheritance or extension | Our approach builds on ... by ... . |
| Specify a difference | Our method differs in how ... is represented / updated / optimized. |
| Explain complementarity | These methods complement ... by providing ... . |

Use method families as subjects for shared properties and individual methods as subjects for distinguishing operations. Vary syntax through the actual relationships: a concession for a tradeoff, a purpose clause for a response to a constraint, or parallel clauses for a direct comparison. Repeated relative clauses or repeated announcements of the current method can obscure those relationships.

## Use Technical Verbs and Concrete Objects

| Purpose | Useful verbs and collocations |
|---|---|
| Describe computation | encode observations into features; predict future states; condition actions on history; aggregate visual tokens |
| Describe development | build on; extend ... to ...; adapt ... for ...; scale ... across ... |
| Describe dependencies and costs | require ...; rely on ...; incur computational cost; increase input length |
| Describe a supported restriction | be restricted to ...; be constrained by ...; limit temporal coverage |
| Position the current work | extend a formulation; integrate information sources; differ in the update mechanism; complement a capability |

Match the verb to the evidence. A required input can be stated directly; a conditional information loss calls for the conditions under which it occurs. Replace vague criticism with the operation, dependency, or measured behavior that matters to the comparison.

Use modifiers for defined properties: recurrent describes updates, task-conditioned identifies conditioning, fixed-size specifies capacity, and structured describes representation organization. Tie evaluations such as efficient or robust to a reported cost or capability.

## Place Citations and Keep the Section Focused

Attach grouped citations to the shared claim they support. When a sentence compares different mechanisms, place each citation with the appropriate clause or named method. Cite a representative separately when its particular design is needed to understand the distinction.

Use the introduction to establish the research problem and related work to explain the technical landscape and nearest comparisons. Develop the details needed for those comparisons while preserving the manuscript's terminology and claim strength. Keep the current method's positioning brief enough that the section continues to explain its relationship to the literature.
