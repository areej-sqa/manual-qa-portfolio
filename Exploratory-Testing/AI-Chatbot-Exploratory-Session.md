# AI Chatbot Exploratory Testing Session

## Session ID
EXP-005

## Feature / Area
AI Chatbot, Conversation Context, Knowledge Base, and Source Citations

## Objective
Explore an AI-powered assistant to identify functional, conversational, grounding, context, citation, privacy, usability, and error-handling issues.

## Test Charter
Explore how the AI assistant handles normal questions, follow-up prompts, unsupported questions, ambiguous requests, uploaded documents, source citations, conversation context, and failures.

Focus on whether responses follow available information, maintain appropriate context, respect user boundaries, and recover correctly from errors.

## Environment
- Platform: Web
- Browser: Google Chrome
- OS: Windows 11
- Environment: Test / Staging
- AI Feature: Sample Knowledge-Based Assistant
- Build: Sample Build 1.0

## Test Data
- Fictional user account
- Sample knowledge-base documents
- Sample uploaded document
- Questions with known answers
- Questions with no available answer
- Ambiguous questions
- Long prompts
- Special characters and Unicode text

## Areas Explored

- Prompt submission
- Response generation
- Multi-turn conversation
- Follow-up questions
- Context retention
- Conversation reset
- Knowledge-base answers
- Source citations
- Uploaded documents
- Unsupported questions
- Regenerate response
- Stop generation
- Error handling
- Conversation privacy
- Responsive behavior

## Scenarios Tested

1. Start a new conversation.
2. Ask a simple question with a known answer.
3. Ask a follow-up question without repeating the original context.
4. Change the topic within the same conversation.
5. Return to the original topic.
6. Ask an ambiguous question.
7. Ask the assistant to clarify an ambiguous request.
8. Ask a question not covered by the knowledge base.
9. Request a source for the answer.
10. Open the provided citation.
11. Verify that the cited document exists.
12. Verify that the cited source supports the response.
13. Ask the same unsupported question using different wording.
14. Upload a supported document.
15. Ask a question answered by the uploaded document.
16. Ask a question not answered by the uploaded document.
17. Upload an unsupported file type.
18. Submit an empty prompt.
19. Submit a very long prompt.
20. Submit Unicode characters and emojis.
21. Rapidly submit multiple prompts.
22. Stop response generation.
23. Regenerate a response.
24. Refresh the page during a conversation.
25. Open the same conversation in another browser tab.
26. Start a new conversation and verify expected context separation.
27. Logout and attempt to reopen the private conversation URL.
28. Login as another test user and attempt to access the first user's conversation.
29. Disconnect the network during response generation.
30. Restore the network and retry.
31. Test the chatbot in a mobile-sized viewport.

## Findings

### Finding 1 — Fabricated Citation
For an unsupported question, the assistant references a document that does not exist in the configured knowledge base.

**Type:** AI Grounding / Citation  
**Status:** Potential Defect

### Finding 2 — Follow-Up Context
The assistant correctly understands a follow-up question without requiring the user to repeat the original subject.

**Type:** Conversation Context  
**Status:** Working as expected

### Finding 3 — Conversation Isolation
A second test user cannot access the first user's private conversation using its direct URL.

**Type:** Privacy / Authorization  
**Status:** Working as expected

### Finding 4 — Network Failure
When the network disconnects during generation, an error message is displayed and the user can retry after connectivity returns.

**Type:** Error Handling / Recovery  
**Status:** Working as expected

### Finding 5 — Rapid Prompt Submission
Multiple prompts can be submitted while an earlier response is still generating, causing responses to appear in an unexpected order.

**Type:** Functional / Conversation State  
**Status:** Requires further investigation

## Defects Identified

Potential issues requiring separate investigation or bug reports:

- AI assistant may fabricate citations for unsupported information.
- Rapid prompt submission may cause conversation responses to appear in an unexpected order.

These findings should be reproduced and confirmed against product requirements before final defect classification.

## Questions / Clarifications

- How should the assistant respond when no supporting source exists?
- Should users be able to submit another prompt while a response is generating?
- Should regenerated answers replace or remain alongside the previous response?
- What conversation context should be retained after starting a new chat?

## Risks

- Fabricated citations may reduce user trust.
- Incorrect context handling may produce misleading responses.
- Conversation-state issues may associate responses with the wrong prompt.
- Incorrect access controls could expose private conversations or documents.

## Follow-Up Testing

Recommended follow-up testing:

- Repeat unsupported questions with different wording.
- Test citations across multiple knowledge-base documents.
- Test conflicting source documents.
- Test longer multi-turn conversations.
- Test multiple uploaded documents.
- Verify conversation isolation at API level.
- Test response generation under slow network conditions.
- Retest confirmed defects after fixes.

## Session Summary

The exploratory session covered AI response generation, conversation context, source grounding, citations, uploaded documents, privacy, network recovery, and conversation-state behavior.

Potential citation-grounding and rapid-submission issues were identified, while follow-up context, conversation isolation, and network recovery behaved as expected in this fictional sample session.

> This is a fictional exploratory testing session created for portfolio demonstration purposes. No real customer conversations, private documents, company information, or production data is included.
