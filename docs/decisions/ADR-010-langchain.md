# ADR-010: LangChain Azure Integration

**Status**: Pending current Azure Search integration verification

## Context

The brief requests LangChain with Azure AI Search and Azure OpenAI; a deprecated chain must not be used by default.

## Options

- Current `langchain-openai` Azure v1 integration plus verified maintained Search vector-store adapter.
- LangChain orchestration with direct Azure AI Search SDK behind an adapter.
- Direct SDK orchestration if LangChain adds unsupported complexity.

## Decision

No Search class/package or chain is selected. Current official LangChain Search page returned 404 during research; verify exact active integration and compatibility before approval. Avoid `ConversationalRetrievalChain` by default.

## Rationale

LangChain docs identify `langchain-openai`, Azure v1 usage, and checkpointer-backed thread memory; Search vector store integration could not be verified from current docs endpoint.

## Consequences

Dependency versions must be pinned; isolate orchestration/retrieval behind boundaries; test hybrid behavior, filters, async/streaming, identity, and model compatibility.

## Dependencies

Current official LangChain docs/package, selected model and Search service, Python runtime, API behavior, security design.

## References

- [LangChain AzureChatOpenAI](https://docs.langchain.com/oss/python/integrations/chat/azure_chat_openai), accessed 2026-11-02.
- [LangChain Azure embeddings](https://docs.langchain.com/oss/python/integrations/text_embedding/azure_openai), accessed 2026-11-02.
- [Azure Search vector-store page used in research](https://docs.langchain.com/oss/python/integrations/vectorstores/azuresearch), retrieved as 404 on 2026-11-02.