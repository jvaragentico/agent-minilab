# Day 1 — Builder Output

## Work completed
Selected a customer-facing AI FAQ and lead-capture assistant as a useful first feature for a small local business.

## Result / implementation proposal

### Problem
Small businesses repeatedly answer questions such as opening hours, location, prices, services, availability, and how to contact or book. Responses may be delayed when staff are busy or the business is closed.

### Feature
Build a lightweight **AI Business Assistant**. A customer types a question in a simple web chat. The assistant answers from business-approved information and, when appropriate, asks for contact details or tells the customer how to reach a human.

### User flow
1. Customer opens the business assistant.
2. Customer asks a question.
3. The application sends the question plus approved business context to the AI.
4. The AI generates a concise answer.
5. If the information is unavailable or uncertain, the assistant says it cannot verify the answer and offers human escalation rather than inventing information.
6. Optionally, the customer can leave a name/contact/request for follow-up.

### Prototype stack
- Next.js for the web interface and server-side application logic.
- OpenAI API for language understanding and response generation.
- Supabase Postgres for approved business information and optional lead records.
- Supabase Auth only if an owner/admin login is added; customer FAQ access does not require an account for the first prototype.
- GitHub for source control.

### Minimum business data
- Business name and description
- Opening hours
- Address/location instructions
- Services/products
- Prices where appropriate
- Contact/escalation method
- FAQ entries
- Explicit information the assistant must never guess

### Implementation steps
1. Create a small structured business profile.
2. Build a single-page chat interface.
3. Add a server-side AI request handler.
4. Retrieve the relevant approved business context for each request.
5. Instruct the model to answer only from supplied business context and flag unknowns.
6. Add a fallback/escalation response.
7. Log test questions and outcomes.
8. Run a fixed evaluation set before showing the prototype.

### Prototype evaluation
Prepare 20 representative customer questions:
- 12 questions whose answers exist in the approved data.
- 5 questions whose answers are deliberately absent.
- 3 ambiguous/adversarial questions.

Target:
- Correctly answer at least 11/12 known-answer questions.
- Refuse or escalate all 5 missing-information questions rather than inventing answers.
- Produce no fabricated price, opening-hour, address, or availability claim.

## Evidence / sources used
- Supabase official documentation states that each project provides a Postgres database and documents database APIs/client access.
- Supabase official documentation states that Supabase Auth supports authentication methods including password and passwordless options.

## Assumptions and uncertainties
- This is a prototype architecture, not a production security design.
- Exact OpenAI model choice, cost limits, multilingual quality, and deployment configuration are intentionally deferred to later exercises.
- Lead collection introduces privacy/data-retention considerations that would need explicit handling before production.

## Unresolved issues
- Define the exact schema for business knowledge.
- Decide how retrieval/context selection will work as business data grows.
- Define production monitoring and abuse controls.
