# LLM interactions — Assignment 1

Tool used: ChatGPT (OpenAI, GPT-6)
Record format: Faithful summaries of exchanges, not verbatim quotations.
Period: Assignment development and analysis, October–November 2026.

1. Understanding the assignment and planning the experiment
Student: Asked for a breakdown of Parts A–G and how to implement a controlled comparison of persona annotators with and without conversation context.
Assistant: Explained the required 20-item human reference, SynDisco discussions, modified persona grid, baseline, two context conditions, raw binary/exact agreement, and two-file submission requirement. Discussed suitable experimental controls.

2. Persona grid, model selection and notebook structure
Student: Requested help choosing a manageable set of personas, model families and an analysis layout suitable for the assignment and local GPU.
Assistant: Helped design the political-outlook × age × gender factorial grid (12 personas plus baseline), compared Qwen2.5-7B, Qwen2.5-3B and Phi-4-mini, and assisted with drafting/revising notebook code, output tables, plotting routines and explanatory Markdown.

3. SynDisco, CUDA and generation troubleshooting
Student: Shared local notebook outputs and errors involving CPU/GPU placement, generation kwargs, checkpointing and overly verbose outputs.
Assistant: Suggested ways to check CUDA placement, avoid passing the same generation setting twice, save complete raw responses, suppress unnecessary progress output and preserve notebook results without rerunning expensive inference. The student ran the actual model calls locally.

4. Conversation generation and reuse
Student: Asked about coherent four-reply discussions and retaining their content for comparison.
Assistant: Discussed the SynDisco discussion interface, sharing the original item with participants, inspecting whether the conversations stay on topic and loading existing conversations rather than regenerating them for every annotation experiment.

5. Parsing rating and evidence separately
Student: Reported excessively high invalid counts and apparently all-toxic predictions, and asked why this was happening.
Assistant: Examined saved raw responses and identified a parser issue: civil ratings were being discarded when the model supplied unnecessary evidence. Helped revise parsing so a clear 1–5 rating is retained while missing, copied, nonverbatim or otherwise noncompliant evidence is flagged separately. Suggested preserving the raw answer and reporting both usable-rating rates and strict compliance.

6. Model-specific prompting and small pilot checks
Student: Asked for documentation-based advice on prompting Qwen and Phi, including appropriate chat templates, fixed severity definitions, evidence quotations and an additional zero-shot versus five-shot comparison.
Assistant: Reviewed relevant model documentation, recommended native tokenizer chat templates, proposed a shared five-point rating rubric with examples and helped create pilot checks of rating distributions and evidence compliance. Student inspected the pilot and executed the full experimental run.

7. Visualization and agreement calculations
Student: Requested clearer plots and statistics covering human agreement, severity distribution, class imbalance, context, examples, and inter-persona/inter-model comparisons.
Assistant: Helped redesign chart titles, labels, model and persona order, denominators, and output exports; drafted/revised calculation and plotting cells. Explained how raw percentage agreement could conceal constant-label behavior.