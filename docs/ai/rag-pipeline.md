# RAG Pipeline

**Status**: Proposed; no orchestration library/class or model deployment is selected.

1. Authenticate caller and resolve trusted organization/principal context.
2. Validate query and load only conversation state bound to that principal and approved organization.
3. Generate query representation with the same approved embedding space used by the index.
4. Execute hybrid lexical/vector retrieval with mandatory authorization filtering.
5. Apply optional reranking only if approved and benchmarked.
6. Construct bounded context from authorized evidence with stable source and location references.
7. Treat retrieved text as untrusted; system policy has precedence, and document text cannot authorize tools or override access.
8. Generate answer or abstain when evidence is missing, conflicting, stale, unauthorized, or insufficient.
9. Validate citations against retrieved authorized records before response.
10. Record safe telemetry and update identity-bound conversation state according to approved policy.

The system must distinguish retrieval failure from model failure and unsupported-answer detection from a successful grounded answer. For conversation persistence, current LangChain guidance uses thread state and a checkpointer; the storage backend and retention remain pending. Do not use deprecated `ConversationalRetrievalChain` without a documented compatibility exception; evaluate current runnable/retrieval patterns during implementation.