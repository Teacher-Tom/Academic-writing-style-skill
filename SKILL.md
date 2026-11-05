---
name: academic-writing-style
description: Draft, revise, and critique Chinese or English academic writing at sentence, paragraph, and manuscript level. Use for concise prose, paper organization, related-work, method, and experiment narratives, consistent terminology, and evidence-aligned claims, especially in CVPR-style ML, computer vision, and VLA papers. Focus on writing rather than a full research or peer-review workflow.
---

# Academic Writing Style

Write direct, concrete, concise academic prose that makes the problem, mechanism, and evidence clear on first reading. Apply to sentence craft, paragraph revision, and manuscript organization in Chinese or English.

## Task and Source Material

- Work from the requested scope, the latest manuscript, and established technical facts. Preserve accepted titles, terminology, paragraph merges, and argument order unless the current request authorizes changes.
- Before drafting, identify the paragraph's central claim and its support. Before revising, understand the causal, temporal, and conditional relationships. Proceed when the available material is sufficient.
- Treat examples as demonstrations of organization. Their architectures, experimental numbers, and novelty claims are not facts about the current manuscript.
- Preserve the manuscript's English variant; use US English for new drafts by default. Communicate in the user's language and script.

## Syntax and Word Choice

- Match subjects to responsibilities: use author subjects for contributions and design choices, modules or variables for computation, and passive constructions when the trained object or experimental setting is the focus.
- Express who performs which operation on what input, and what it produces. Prefer verbs with concrete objects, such as encode, compress, update, retrieve, condition, align, and optimize.
- State the core operation or claim in a clear main clause, then add purpose, conditions, concessions, or results. Limit modifiers between subject and predicate; distribute architecture, losses, data, and effects across appropriate sentences.
- Let the operation causing a limitation serve as the subject when useful. Connect the operation to its direct consequence and then to its effect on the task. Use clauses to make both internal and intersentence relationships traceable.
- Use short sentences for central judgments and longer ones for mechanisms or conditions when appropriate. Let content determine length; impose no word-count, clause-count, or punctuation quotas.
- Use modifiers to specify technical properties, comparison targets, and experimental conditions. Usually remove promotional adjectives, empty emphasis, and self-evaluation.
- Avoid defensive phrasing, repeated rhetorical questions, forced corrective contrasts, repeated statements of what was not done, and unnecessary metadiscourse.
- Use qualifiers for real uncertainty and evidence boundaries. State confirmed implementation details directly rather than wrapping every claim in vague caution.

## Paragraphs and Argument

- Give each paragraph a clear function: establish a constraint, explain a limitation, introduce an idea, describe a mechanism, present evidence, or interpret a result. Let that function determine its length and structure.
- Explain limitations through mechanisms or concrete situations and their task consequences. Go beyond lists of symptoms such as low efficiency, weak generalization, or limited capability.
- Introduce the central design idea before following the information flow. Make inputs, representations, state updates, outputs, and supervision relate clearly to one another.
- Open the next sentence with established information when useful. An output can become the next subject, and a defined representation can become the condition for the next operation. Reuse stable terminology to track objects, states, and updates.
- Mark purpose, concession, contrast, progression, and consequence explicitly when needed. Choose clauses or sentence transitions according to the reading flow. Preserve necessary links without mechanically prefacing every sentence with a connector.
- Narrow introductions from application constraints to a specific problem, then outline the method and evidence. Keep contribution statements parallel and distinguish their mechanisms, supervision, or capabilities.
- Organize methods around computational relationships. Build result paragraphs around the evaluation question, key finding, selected quantitative evidence, and interpretation. Adapt structure to the section's function.
- In method prose, connect a local design goal to the computation and its role. Use equations to specify relationships and prose to explain quantities, dependencies, and consequences.
- Organize related work by technical routes and comparison axes tied to the current problem. Group citations for shared mechanisms and expand on the closest methods. Explain how the current work builds on, extends, differs from, or complements those routes.
- When discussing prior work, connect a capability with its cost under the same technical tradeoff. Explain limitations through the design causing them and their task consequences. Ground the comparison's scope in the cited methods and settings.

## Manuscript Organization

- Let the central contributions guide section and subsection boundaries. Connect each claim to its design and supporting evidence; distinguish completed experiments from proposed analyses.
- Order methods by conceptual and computational dependencies. Establish the task and system interface before explaining internal mechanisms. Make supervision targets, signals, and optimized parameters explicit, and distinguish training stages from the deployed inference path.
- Organize experiments around the claims being tested and state the conditions that determine each comparison's meaning. Where relevant, connect representation quality to downstream utility and present efficiency together with task performance.
- Allocate main-text space to the definitions, mechanisms, and evidence needed to assess the contribution. Use supplementary material for expanded implementation details and supporting results. Choose related-work placement, separate data or discussion sections, and experiment order to fit the paper.

## Terminology, Evidence, and Citations

- Define names and abbreviations on first use and reuse them consistently. Distinguish input data, latent representations, states, modules, and training objectives; do not rotate near-synonyms merely to avoid repetition.
- Preserve technical meaning and claim strength. Training objectives, intended benefits, empirical observations, causal explanations, and formal guarantees are distinct. Do not turn a lack of direct optimization into a claim of complete inability.
- Report results with their task, metric, baseline, and conditions. Preserve units, denominators, and the distinction between relative percentages and percentage points. Separate prediction horizon, execution horizon, observation rate, and action rate.
- Match efficiency claims to the measured quantity: module runtime, end-to-end latency, throughput, or critical-path overhead. Asynchronous overlap alone does not establish zero additional latency.
- Place citations next to the claims they support. Add only verified sources and facts. Distinguish a source's publication status, observations about its prose, and mandatory conference requirements.
- Present tense usually suits technical processes, contributions, and findings shown in figures or tables. Use past tense for specific past events when appropriate and keep temporal relationships clear.

## Editing and Delivery

- Repair the argument and information order before tightening sentences, checking terminology, and reviewing citations. Remove repeated claims, dispensable transitions, and sentences without substantive information.
- Preserve user edits outside the requested scope. Maintain LaTeX labels, citation keys, equations, and macros; follow the project's compilation and preview workflow when structure or layout is affected.
- Deliver the requested prose, files, or feedback. Explain choices that affect technical meaning; keep routine revision reports brief.

For clause organization, logical transitions, verb collocations, and paragraph examples, read [references/patterns.md](references/patterns.md).
For related-work organization, comparison sentences, and technical positioning, read [references/related-work.md](references/related-work.md).
For method exposition, equations, learning objectives, and training/inference descriptions, read [references/method-writing.md](references/method-writing.md).
For experimental setup, result paragraphs, ablations, efficiency reports, and figure/table language, read [references/experiment-writing.md](references/experiment-writing.md).
For paper outlines, section organization, and experimental narratives, read [references/manuscript-structure.md](references/manuscript-structure.md).
When asked to study CVPR/VLA writing or trace this skill's reading basis, read [references/cvpr-vla-examples.md](references/cvpr-vla-examples.md). It includes observations on syntax, related work, methods, experiments, and whole-paper organization from CVPR 2025-2026 papers. These examples are not mandatory templates.
