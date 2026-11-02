# Prompt Engineering

**Status**: Security and behavior requirements; actual prompt text is not defined.

Prompt design must separate trusted system policy, user request, and untrusted retrieved evidence. It must instruct the model to answer only from supplied authorized evidence, identify insufficient or conflicting evidence, and cite source references using an explicit application-controlled mapping. Retrieved documents must never be treated as instructions, tool grants, identity claims, or policy overrides.

Prompts and model behavior require versioning and evaluation. Changes must be tested against groundedness, citation correctness, abstention, prompt injection, data disclosure, and supported language cases. Avoid putting secrets, unnecessary personal data, access tokens, or raw policy documents in prompt templates. Numeric acceptance thresholds and exact model version are pending approval.