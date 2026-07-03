# Prompt-Tuning-for-legal-document-summarization-using-T5

Prompt-Tuning-for-Legal-Document-Summarization-using-T5

This repository provides a two-stage method of soft prompt tuning based on a frozen T5 model towards abstractive summarization of In-Abs dataset. The target is to fine-tune the prompt embeddings only and use them in other T5 models for few-shot or zero-shot generalization. Performance is also compared with a fine-tuned baseline T5 summarization model.

Project Workflow

Soft Prompt Tuning
Train soft prompts on a summarization task on a frozen T5 model (e.g., t5-small).
Only the prompt embeddings are updated; the other model parameters are frozen.
Dataset employed: IN-Abs legal dataset with judgement/ and respective summary/.

Prompt Embedding Extraction
Retrieve the soft prompt embeddings learned with training.
Save these embeddings for use in a future downstream model.
Evaluation on Another T5
Load a frozen standalone T5 model.
Append the acquired soft prompt embeddings to the input token embeddings.
Generate the summaries on the test set from this updated input.
Compare the generated summaries with gold summaries according to standard metrics.
Baseline Summarization Model
Generate summary using vanilla t5 model without any embeddings.

Experimental Objectives

This project is for:
Demonstrate the effectiveness of soft prompt tuning for legal summarization.

Evaluate whether prompt embeddings can generalize when applied to another T5 model.
