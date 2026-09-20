# BUG-009 — AI Assistant Fabricates Source Citation

## Bug ID
BUG-009

## Title
AI assistant provides a citation to a source that does not exist in the available knowledge base.

## Environment
- Platform: Web
- Browser: Google Chrome
- OS: Windows 11
- Environment: Test / Staging
- AI Feature: Knowledge-Based Assistant
- Build: Sample Build 1.0

## Severity
High

## Priority
High

## Preconditions
- User is logged in.
- AI assistant is available.
- The assistant is configured to answer questions using an approved test knowledge base.
- The test knowledge base does not contain information about the selected test topic.

## Steps to Reproduce

1. Login with a valid test account.
2. Open the AI assistant.
3. Ask a question about information that is not available in the configured knowledge base.
4. Ask the assistant to provide the source for its answer.
5. Review the generated response and citation.
6. Search the configured knowledge base for the cited source.

## Expected Result
The assistant should indicate that the requested information is not available in the provided sources or clearly distinguish unsupported information according to product requirements.

It should not invent a document, URL, title, or citation.

## Actual Result
The assistant provides an answer and references a document that does not exist in the configured knowledge base.

The citation appears valid in the response but cannot be found or opened.

## Reproducibility
4/5 — Frequently

## Evidence
- Chat screenshot: Not included — sample portfolio report
- Screen recording: Not included — sample portfolio report
- Knowledge-base comparison: Not included — sample portfolio report

## Additional Notes
This issue can reduce user trust because the generated citation gives the impression that the response is supported by an existing source.

Testing should also cover:
- Questions with no matching source.
- Conflicting source documents.
- Follow-up questions referencing previous answers.
- Citations after conversation regeneration.
- Uploaded-document questions.
- Source links that exist but do not support the generated claim.

> This is a fictional bug report created for portfolio demonstration purposes. No real conversations, private documents, customer information, or company data is included.
