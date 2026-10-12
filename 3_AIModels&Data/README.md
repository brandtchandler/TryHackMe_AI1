# TryHackMe - AI Models & Data

**Platform**: TryHackMe  
**Difficulty**: Medium  
**Category**: AI Security  
**Date**: 11 Oct 2026  
**Time spent**: ~2 hours (including write-up)  
**Tags**: `#AI-models` `#MachineLearning` `#cybersecurity` `#black-box`

---

## Summary

This room covers key risks inherent in AI security. It builds a clearer understanding of training and model building, and highlights the problems that arise with fine-tuning.

## Key Takeaways

- **Data is the root risk** — Most organisations cannot answer where their training data came from or whether it was tampered with.
- **PII and credentials get permanently baked in** via web scraping and cannot be patched out after deployment.
- **Fine-tuning inherits everything** — biases, vulnerabilities, and weakened safety alignment from the base model.
- **Models are un-auditable** — You can only test behaviour (sampling); you cannot inspect the billions of weights inside.

---

## Learning Objectives & Tasks

**7 tasks in total**

### Task 1 – Intro

Sets the scene for what you will learn and focus on. Encourages you to recall prior knowledge. Pay attention to key vocabulary. Establishes the room’s objectives.

### Task 2 – Training Data

AI/ML models are trained on data. GPT-3, for example, was trained on 570 GB of filtered text. Training data typically falls into four buckets:

1. **Web scraping** – Data collected via web crawling → **Low trust**
2. **Licensed datasets** – Purchased or owned platform data → **Medium trust**
3. **Synthetic data** – AI-generated content used to train other AI systems → **Variable trust** (≈12 % of fine-tuning data is now LLM-generated)
4. **Internal corpora** – Company knowledge and proprietary data → **High trust** (controlled, but the organisation is liable for mishandling)

#### Understanding Provenance

Data provenance is the ability to answer three questions about any piece of training data:

1. Where did it come from?
2. When was it collected?
3. Has it been modified since?

In today’s AI supply chain the answer to all three is usually “we don’t fully know.” More than 70 % of data is listed as unspecified. The **Data Provenance Initiative** audited datasets and found that, on top of the 70 %, 66 datasets were miscategorised. What is inside these models is therefore largely unknown.

This is not a new lesson. SolarWinds taught the industry that you cannot trust a binary when you do not know what went into it. That is why Software Bills of Materials (SBOMs) became standard practice. The equivalent for machine learning is the **ML-BOM** — a documented inventory of the datasets used. Adoption is still early.

One consequence of heavy reliance on scraped data is that personal information ends up inside the models. Security researchers have recovered API keys and passwords from Common Crawl data. Once this information is baked into a trained model it cannot be filtered out. Model behaviour is a direct result of what it was trained on.

### Task 3 – Building the Model

Moving from the high-level picture of “data in → model out” to the practical process of training.

- An **epoch** is one complete pass of the algorithm over the entire training dataset. Models typically run for many epochs until they can make accurate predictions.
- More epochs do **not** automatically produce a better model. Train too long and the model stops learning general patterns and simply memorises the training data — this is called **overfitting**. An overfitted model performs well on the training set and poorly on any other data.

To detect overfitting, a portion of the data is held back as a **validation set**. The model is evaluated on this unseen data at regular intervals. If training accuracy continues to rise while validation accuracy plateaus or falls, overfitting is occurring.

#### Post-training Optimisation

| Technique      | Description                                                                 | Security Considerations                                                                 |
|----------------|-----------------------------------------------------------------------------|------------------------------------------------------------------------------------------|
| **Pruning**    | Removes parameters that contribute little to predictions, shrinking model size | Changes model behaviour after training; rarely documented in detail                     |
| **Quantisation** | Reduces numerical precision of weights to cut memory and compute requirements | Can degrade safety-aligned behaviour; backdoor defences tested on full-precision models may fail on quantised versions |

#### Federated Learning

The model is trained across decentralised devices or organisations. Each participant keeps its own data locally and only sends weight updates to a central server for aggregation. This protects the privacy of the underlying datasets, but makes integrity much harder to verify. In a centralised system the owner controls the data; in a federated system no single party can fully authenticate what data was used.

### Task 4 – The Inheritance Problem

Training a new LLM from scratch can require trillions of tokens and enormous infrastructure cost. For most organisations this is impractical, so they start from a pre-trained model and **fine-tune** it.

- **Pre-trained model** – A model that already has broad language understanding.
- **Fine-tuning** – Continuing training on a smaller, domain-specific dataset (e.g., medical literature for healthcare, case law for legal).

**What fine-tuning changes**  
Task-specific behaviour, tone, and domain knowledge.

**What fine-tuning does *not* change**  
The base-model weights — the billions of parameters formed during pre-training on data the fine-tuning organisation never saw and almost certainly never audited.

#### The Inheritance Problem

When you adopt someone else’s model you inherit its baked-in biases, strange behaviours, and any weakened safety alignments. This surfaces in three ways:

1. **Safety alignment erodes, it does not break**  
   Fine-tuning can gradually strip away previously installed safety features.

2. **Specialisation increases the attack surface**  
   Cisco research showed that fine-tuned models are more susceptible to prompt injection and present larger attack surfaces than their base counterparts. The narrowed focus gives attackers clearer vectors for manipulation.

3. **Version matters — and is rarely tracked**  
   Fine-tuning targets a specific checkpoint of a base model. Later adopters inherit every flaw, backdoor, or problem present in that checkpoint.

### Task 5 – The Black Box Problem

Traditional software can be compiled down to binary and, with enough effort, disassembled and understood. Trained models are different: they consist of billions of floating-point numbers that are not human-readable. You cannot open a model and determine why it behaves the way it does, nor can you see exactly what it was trained on.

Behavioural testing is possible, but it is sampling, not a true audit. You are forced to trust the original training process.

#### Model Cards

A **model card** is a structured document that accompanies a model and describes what it is, how it was built, and where it falls short. Introduced in 2019 by Google researchers, model cards are becoming a de-facto standard. A good model card answers questions that cannot be answered by inspecting the weights:

- **Training Data** – Sources used, filtering applied, known gaps or biases
- **Intended Use** – What the model was designed for (and explicitly what it was not)
- **Evaluation Results** – Performance metrics
- **Known Limitations** – Conditions under which the model behaves abnormally or underperforms
- **Bias Assessment** – Where training data or evaluation may have introduced skew
- **License** – What you are legally permitted to do with the model

#### The Gaps

Proper documentation of the datasets that trained modern AI systems is still missing or incomplete. While model cards are an improvement, they remain voluntary and frequently incomplete. From a security perspective this is the beginning of a nightmare: without an audit trail or a model card, these systems are complete black boxes.

### Task 6 – Practical

Enter the View site (designed to resemble Hugging Face) and begin your model audit. Explore the interface and classify any issues you discover as high, medium, or low severity.

### Task 7 – Conclusion

**Key points**

- AI training data is poorly documented — whether by design or by accident.
- PII and credentials can become permanently baked into a model.
- Quantisation and federated learning introduce their own security trade-offs.
- Fine-tuning a pre-trained model inherits everything that came with it, often eroding safety alignment and increasing vulnerability to prompt injection.
- Trained model weights are opaque. Security testing can only sample behaviour; model cards are voluntary, incomplete, and sometimes absent.

---

## Final Summary

The “black box” nature of modern AI means we rarely understand what is inside these models. We can tweak them, but every tweak can also introduce new vulnerabilities. Evaluation techniques and voluntary documentation (model cards) help, yet gaps remain. Fine-tuning is essential for industry-specific use cases, but it also imports the risks of the base model. Learning how to evaluate AI systems is therefore becoming a core security skill.
