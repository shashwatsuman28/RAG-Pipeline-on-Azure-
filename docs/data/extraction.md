# Document Extraction

**Status**: Azure AI Document Intelligence v4 is a researched candidate, not an accepted service selection.

Microsoft documents v4.0 (`2024-11-30`) as GA/current. Its SDK pairing table lists Python `azure-ai-documentintelligence` 1.0.0 for v4; PyPI lists 1.0.2 on the research access date, so verify package/API compatibility before pinning. The v4 layout model extracts text and structure, tables for supported formats, and source regions. Its model-specific format support and constraints matter: embedded/linked images in Office documents are not analyzed; current Microsoft v4 pages conflict on Excel extensions (one lists XLS while another discusses XLSX worksheet accounting), and XLSX table extraction is documented as unsupported. Confirm exact Excel input support for the selected API/model and fixture before committing a format guarantee. Arbitrary key-value extraction is not guaranteed by layout. Prebuilt models return defined fields for supported document categories; custom extraction introduces training/data governance decisions.

Proposed extraction output includes API/model version, source revision, text/paragraph/table/key-value elements only when returned, page/element location where available, partial status, and errors. A fixture matrix must establish actual quality and supported limits. Entra authentication requires a custom subdomain; verify the selected resource type and Python credential path.

Sources and exact limits are recorded in [research.md](../../specs/001-documentio-platform/research.md). No extraction was run.