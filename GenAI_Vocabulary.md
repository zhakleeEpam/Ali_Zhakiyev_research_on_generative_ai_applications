# GenAI Vocabulary — Key Terms for Practitioners

This glossary lists concise, high-value terms you should know and use when acting as a subject-matter expert in generative-AI application development and usage. Each entry includes a short definition, why it matters, and an example usage phrase.

---

- **LLM (Large Language Model):** A neural network trained on large corpora of text to generate or understand language. Why it matters: core building block for text generation, summarization, and conversational agents. Example: "We evaluated two LLM variants for latency and factuality."

- **Token / Tokenization:** The unit of text (subword/wordpiece) that a model processes; tokenization is the mapping from raw text to tokens. Why it matters: token counts determine cost, context limits, and truncation behavior. Example: "Trim prompts to 1,024 tokens to fit the model's context window."

- **Context Window / Context Length:** The maximum number of tokens an LLM can attend to in a single forward pass. Why it matters: limits long-document reasoning and multi-turn history. Example: "Use retrieval to include long history because the model has a 4k token context window."

- **Prompt Engineering:** The craft of designing prompts or templates to elicit desired model behavior. Why it matters: simple prompts can greatly change output quality and safety. Example: "Add an explicit format instruction at the top of the prompt."

- **Instruction Tuning / SFT (Supervised Fine-Tuning):** Fine-tuning a base model on instruction-response examples to make it follow prompts better. Why it matters: improves controllability and usefulness for end tasks. Example: "We instruction-tuned the model on 10k QA pairs for better assistant responses."

- **RLHF (Reinforcement Learning from Human Feedback):** Using human preferences to further train models with reinforcement learning to improve aligned behavior. Why it matters: reduces undesirable outputs and improves helpfulness. Example: "RLHF reduced aggressive responses in the assistant."

- **Fine-tuning (Full / PEFT / LoRA):** Adapting a model to a task; PEFT (Parameter-Efficient Fine-Tuning) methods like LoRA change fewer weights to save compute. Why it matters: customizes models without retraining massively. Example: "We used LoRA to fine-tune on domain text with limited GPU memory."

- **Quantization (int8 / int4):** Reducing numerical precision of weights/activations to shrink model size and speed inference. Why it matters: enables lower-cost deployment and edge inference. Example: "Quantizing to int8 cut GPU memory by ~2x with minor quality loss."

- **Distillation / Knowledge Distillation:** Training a smaller 'student' model to imitate a larger 'teacher' model. Why it matters: creates efficient models for production while preserving performance. Example: "Distillation produced a 3× faster model for mobile clients."

- **Hallucination:** When a model generates plausible-sounding but incorrect or fabricated information. Why it matters: a primary source of trust and safety failures. Example: "The model hallucinated a citation not present in the knowledge base."

- **Grounding / Retrieval-Augmented Generation (RAG):** Combining retrieval (vector or DB) with generation so responses cite or depend on external documents. Why it matters: improves factuality and provenance. Example: "We use RAG to ground answers in the customer's policy docs."

- **Embeddings:** Numeric vector representations of text (sentences, docs) that encode semantic similarity. Why it matters: basis for semantic search, clustering, and RAG. Example: "Store paragraph embeddings in a vector index and query nearest neighbors."

- **Vector Index / Vector DB / ANN (e.g., FAISS, HNSW, Pinecone):** Data structures and services for fast nearest-neighbor search over embeddings. Why it matters: enables scalable semantic retrieval. Example: "Use HNSW for sub-second nearest-neighbor lookups."

- **Provenance / Attribution:** Tracking the source and lineage of content and model outputs. Why it matters: required for audits, compliance, and reducing hallucinations. Example: "Include provenance metadata with every generated answer."

- **Model Drift / Data Drift:** When model behavior or input data distribution changes over time, reducing performance. Why it matters: necessitates monitoring and retraining. Example: "We detected concept drift after a product redesign and scheduled a retrain."

- **Evaluation Metrics (Factuality, ROUGE, BLEU, Perplexity, Human Eval):** Quantitative and human measures for quality assessment. Why it matters: choose metrics aligned with business goals. Example: "Perplexity improved but human eval flagged lower factuality."

- **Safety / Alignment:** Techniques and practices ensuring models follow desired norms and avoid harmful outputs. Why it matters: compliance, user trust, and risk mitigation. Example: "We applied safety filters and an on-call review workflow for flagged outputs."

- **Filtering / Moderation / Guardrails:** Automated and human checks to block disallowed content. Why it matters: prevents abuse and legal exposure. Example: "Responses pass through a moderation filter before returning to users."

- **Watermarking (Model Watermarks):** Methods to embed a detectable signature into generated content for provenance and misuse detection. Why it matters: attribution and abuse detection. Example: "We add a subtle watermark to AI-generated articles."

- **Differential Privacy / DP-SGD:** Techniques to protect training data privacy by limiting influence of individual records. Why it matters: regulatory and ethical compliance for sensitive datasets. Example: "Training with DP-SGD reduced leakage risk for user data."

- **Federated Learning:** Decentralized training where clients keep data locally and share model updates. Why it matters: privacy-preserving collaboration across devices or organizations. Example: "Federated fine-tuning allowed personalization without centralizing PII."

- **On-Prem / Edge Inference:** Running models within customer-controlled infrastructure or on-device versus cloud inference. Why it matters: data residency, latency, and cost trade-offs. Example: "On-prem inference satisfied the bank's data residency requirements."

- **Multimodal:** Models that handle multiple modalities (text, image, audio, video). Why it matters: enables richer user experiences (e.g., visual QA, captioning). Example: "We built a multimodal assistant for image-inspection workflows."

- **Chain-of-Thought (CoT):** Prompting or training technique that encourages models to generate intermediate reasoning steps. Why it matters: can improve complex problem solving and explainability. Example: "Enable CoT prompts for multi-step math reasoning."

- **Prompt Template / Prompt Chaining:** Re-usable prompt formats or sequences of prompts that structure complex tasks. Why it matters: standardizes behavior and simplifies maintenance. Example: "Use a prompt template for policy-compliant summarization."

- **Temperature / Top-k / Top-p (Nucleus Sampling):** Decoding hyperparameters controlling randomness/diversity of generated text. Why it matters: tune for creativity vs. determinism. Example: "Set temperature=0.2 for factual outputs and 0.8 for creative copy."

- **Greedy / Beam Search / Sampling:** Decoding strategies with different trade-offs between speed, diversity, and optimality. Why it matters: affect response quality and latency. Example: "Beam search improved answer accuracy but increased latency."

- **Throughput / Latency / Cost-per-call:** Operational performance and billing considerations for inference. Why it matters: impacts UX and product economics. Example: "We optimize batch size to increase throughput and lower cost-per-call."

- **Autoscaling / Load Balancing:** Infrastructure patterns for handling variable inference traffic. Why it matters: reliability and cost-efficiency. Example: "Autoscaling kept latency stable during traffic spikes."

- **Model Registry / Model Card:** Tools and documentation for tracking model versions, metadata, and intended use. Why it matters: governance and reproducibility. Example: "Upload each release with a Model Card documenting limits and training data scope."

- **Dataset Card / Datasheet:** Structured documentation describing dataset provenance, collection methods, and limitations. Why it matters: transparency and data governance. Example: "Attach a Datasheet to any training dataset used for compliance reviews."

- **Licensing & Copyright (Training Data Rights):** Legal constraints around using datasets and generated outputs. Why it matters: reduces litigation and IP risk. Example: "Verify dataset licenses before using content for model training."

- **Synthetic Data / Data Augmentation:** Artificially generated data to expand training sets or protect privacy. Why it matters: addresses class imbalance and privacy requirements. Example: "Use synthetic examples to boost rare-case performance."

- **Adversarial Testing / Red-Teaming:** Stress-testing models to find failure modes and safety vulnerabilities. Why it matters: uncovers risks before production release. Example: "We ran a red-team exercise to probe prompt injection attacks."

- **Prompt Injection / Jailbreaks:** Attacks that manipulate prompt context to make models reveal secrets or violate policies. Why it matters: security risk in multi-tenant or untrusted input scenarios. Example: "Sanitize user prompts to reduce prompt-injection risk."

- **Retrieval Context Chunking / Overlap Strategy:** How documents are split before embedding (size and overlap). Why it matters: affects retrieval precision and answer completeness. Example: "We use 1,000-token chunks with 200-token overlap for long documents."

- **Hybrid Retrieval (BM25 + Embeddings):** Combining lexical and semantic search for better coverage. Why it matters: improves recall and precision in practical systems. Example: "Hybrid retrieval gave better results on short queries."

- **Observability / Monitoring (Latency, Errors, Drift, Safety Alerts):** Systems to track runtime model health and quality. Why it matters: enables rapid detection and remediation. Example: "Set alerts for increases in hallucination rates or API error spikes."

- **Cost Estimation (Compute FLOPs, Inference cost, Training cost):** Quantifying resources needed to train and serve models. Why it matters: budgeting and architecture tradeoffs. Example: "We estimated training FLOPs to decide between full fine-tuning vs. PEFT."

- **MLOps / ModelOps:** Processes and tooling for continuous training, deployment, and governance of models. Why it matters: production-grade lifecycle management and compliance. Example: "Implement MLOps pipelines for retraining and deployment rollbacks."

- **Backup & Rollback / Canary Deployments:** Safe deployment patterns to reduce risk when releasing model updates. Why it matters: minimizes exposure to regressions. Example: "Deploy new model to 5% of traffic via canary before full rollout."

- **Explainability / Interpretability:** Techniques that help understand model decisions (saliency, attention analysis, rationale). Why it matters: trust, debugging, and regulatory reasons. Example: "Provide an explainability view for analysts investigating flagged outputs."

---

If you'd like, I can:
- convert this glossary into a one-page cheat sheet for onboarding;
- add links to canonical references and tutorials for each term; or
- export it as PDF or slides for presentations.

File: `GenAI_Vocabulary.md`
