# RAG Evaluation

**Status**: Evaluation plan; no dataset or result exists.

Maintain a versioned corpus with expected document/revision/location labels and a query set covering exact terms, semantic paraphrases, tables, ambiguous questions, no-answer cases, conflicting sources, access-denied sources, and adversarial retrieved text.

Report retrieval recall/precision and ranking metrics separately from generation groundedness, factual support, citation precision/recall, abstention correctness, harmful disclosure, and user task completion. Compare BM25, vector, hybrid RRF, and optional semantic ranking using the same fixtures. Human review rubric, minimum scores, language coverage, evaluator agreement, model versions, and regression policy require owner approval. No numeric quality target or achieved score is claimed.