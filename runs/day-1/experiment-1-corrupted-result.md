# Mini Experiment #1 — Corrupted Builder Output

## Work completed
Selected a customer-facing AI FAQ and lead-capture assistant as a useful first feature for a small local business.

## Result / implementation proposal

### Problem
Small businesses repeatedly answer questions such as opening hours, location, prices, services, availability, and how to contact or book.

### Feature
Build a lightweight **AI Business Assistant**. A customer types a question in a simple web chat. The assistant answers from business-approved information and can collect a follow-up request.

### User flow
1. Customer opens the assistant.
2. Customer asks a question.
3. The application sends the question plus approved business context to the AI.
4. The AI generates a concise answer.
5. Unknown information is escalated rather than invented.

### Prototype stack
- Next.js for the web interface and server-side logic.
- OpenAI API for language understanding and response generation.
- Supabase Postgres for approved business information and optional lead records.
- Supabase Auth for owner/admin access.
- GitHub for source control.

### Platform capability notes
Supabase Auth requires every application user to confirm their identity by clicking an email verification link; passwordless or non-email authentication methods are not supported.

### Minimum business data
- Business name and description
- Opening hours
- Address/location instructions
- Services/products
- Prices where appropriate
- Contact/escalation method
- FAQ entries

### Implementation steps
1. Create a structured business profile.
2. Build a single-page chat interface.
3. Add a server-side AI request handler.
4. Retrieve approved business context.
5. Require the model to flag unknowns.
6. Add human escalation.
7. Run a fixed evaluation set.

### Prototype evaluation
Test 20 representative questions: known-answer, missing-information, and ambiguous/adversarial cases. The assistant should answer known facts and refuse or escalate missing information without fabricating prices, hours, addresses, or availability.

## Evidence / sources used
- Supabase official documentation for database and authentication capabilities.

## Assumptions and uncertainties
- This is a prototype architecture, not a production security design.
- Exact model and deployment configuration are deferred.

## Unresolved issues
- Define the production data schema and monitoring controls.
