# Method Writing: Computation, Equations, and Learning

Use for method sections and technical mechanism descriptions. Preserve established facts and notation. Choose the presentation order from the dependencies readers need to understand; adapt local explanations to the complexity of the operation.

## Establish the Interface and Information Flow

Explain the available inputs, outputs, and any maintained state before detailing the modules that transform them. Introduce intermediate representations where their computational role becomes clear. Let the output of one operation become the input or subject of the next, using consistent names and notation.

Distinguish raw inputs, contextualized features, latent states, and predicted outputs. In temporal systems, identify which previous states and observations are available at each update or prediction. Conditioning sets should reflect that availability.

## Explain a Local Design

A useful progression is local goal or constraint, concrete computation, mathematical definition, and the output's role or a relevant computational property. Include the moves needed to explain the design without imposing a fixed paragraph length.

State the design choice and then show how it operates. When an efficiency property follows from a particular computation, explain the connection, such as skipping inactive elements or reusing cached features. Identify empirical design choices through the corresponding evidence or experiment reference. Keep intended learning benefits distinct from demonstrated outcomes.

## Coordinate Prose and Equations

- Introduce what an equation computes or optimizes before displaying it. Define new symbols, indices, and any necessary dimensions, ranges, or units near their use.
- Use the surrounding prose to explain the roles of quantities, the source of supervision, and how the output enters the next operation. Select details that resolve ambiguity rather than restating every symbol in words.
- Distinguish parameters, observations, predictions, targets, and recurrent states in notation. Specify time indices and conditioning when they determine the computation.
- Preserve consistency among prose, equations, overview figures, and algorithms. A diagram or equation should express the same inputs, state transitions, and update order as the text.
- Use equations where they clarify dependencies, objectives, or a substantive transformation. Explain an adopted component at the interface and modification needed for the paper, citing its source for additional details.

## Relate Objectives to Training and Deployment

For each substantive objective, explain the predicted quantity, target or reward, supervision source, and parameters it optimizes. Give loss weights or schedules where they affect the method's interpretation. Distinguish objectives applied jointly from those used in separate stages.

Make parameter updates and freezing explicit when they determine what the model learns. A representation can condition a policy without receiving gradients from the policy loss; describe the actual training relationship.

Separate training stages from the inference path. Identify auxiliary components or targets used during training and specify which modules run during deployment. For sequential or asynchronous systems, distinguish observation, state-update, prediction, and execution schedules. Explain the runtime information flow in the order operations occur.

## Choose Sentences by Their Function

These are original templates. Fill them with the actual objects, operations, and conditions; choose author, module, or state subjects according to responsibility.

| Function | Possible structure |
|---|---|
| Define the task | Given ..., our goal is to predict ... . |
| Define a representation | We represent ... as ..., where ... denotes ... . |
| Describe a computation | The encoder maps ... into ... . |
| State a design purpose | To preserve ..., we update ... using ... . |
| Express conditioning | Conditioned on ..., the policy predicts ... . |
| Describe recurrence | At each update step, ... integrates ... with its previous state. |
| Introduce an equation | We compute ... as follows: ... . |
| Explain symbol roles | Here, ... denotes ..., and ... controls ... . |
| Specify optimization scope | We minimize ... with respect to ..., keeping ... fixed. |
| Describe learning stages | We first train ... on ..., then optimize ... using ... . |
| Describe inference | At inference, ... reads ... and generates ... . |
| Explain a computational property | By ..., the module ... . |

Let authors describe design choices, modules perform computation, and states carry information between operations. Use purpose clauses for motivations, temporal clauses for schedules, and conditioning clauses for dependencies. Choose the form that exposes the relationship instead of repeating the same introductory phrase.

## Match Verbs to Operations

| Operation | Useful collocations and distinctions |
|---|---|
| Representation | Encode observations into features; embed instructions; parameterize a state. Compression additionally requires explaining the reduced representation budget. |
| Feature transformation | Project features into an embedding space; concatenate embeddings; aggregate tokens. Specify the actual transformation when a general term such as fusion leaves the computation unclear. |
| State maintenance | Update a state; integrate new evidence; retain prior information. Retrieval reads stored information, whereas an update changes the state. |
| Prediction and generation | Predict actions; decode latent features; reconstruct observations; generate a sequence. Identify the predicted object and the operation producing it. |
| Supervision and optimization | Supervise predictions; minimize a loss; optimize parameters. Distinguish the training signal, objective, and variables being updated. |
| Transfer and alignment | Distill representations; align hidden states; transfer a capability. Specify the teacher, student, comparison target, or alignment quantity. |
| Runtime | Cache features; reuse states; sample actions; execute an action sequence. Distinguish generated outputs from executed outputs and specify stopping behavior where relevant. |

## Allocate Detail by Its Role

Give novel mechanisms and behavior-determining choices enough detail to be understood and assessed. Keep essential training logic, information dependencies, and operating assumptions in the main text. Expanded implementation details and standard derivations can go in supplementary material when they are not central to the contribution.

For source-specific observations, see [the CVPR method reading](cvpr-vla-examples.md#method-writing-reading). For section-level organization, see [manuscript-structure.md](manuscript-structure.md).
