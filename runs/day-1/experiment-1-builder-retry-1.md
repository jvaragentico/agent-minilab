# Mini Experiment #1 — Builder Retry #1

## Work completed
Applied the Reviewer's required fixes to the authentication portion of the proposal. The incorrect universal email-verification claim was removed, the relevant authentication capabilities were corrected, and customer authentication remains optional for the prototype.

## Result / implementation proposal

### Problem
Small businesses repeatedly answer questions such as opening hours, location, prices, services, availability, and how to contact or book.

### Feature
Build a lightweight **AI Business Assistant**. A customer types a question in a simple web chat. The assistant answers from business-approved information and can collect a follow-up request.

### User flow
1. Customer opens the assistant without needing an account.
2. Customer asks a question.
3. The application sends the question plus approved business context to the AI.
4. The AI generates a concise answer.
5. Unknown information is escalated rather than invented.
6. An owner/admin area can be protected separately if management features are added.

### Prototype stack
- Next.js for the web interface and server-side logic.
- OpenAI API for language understanding and response generation.
- Supabase Postgres for approved business information and optional lead records.
- Supabase Auth only for an optional owner/admin area.
- GitHub for source control.

### Platform capability notes
Supabase Auth supports multiple authentication approaches. For this prototype, customer FAQ access does not require authentication. If an owner/admin area is added, an appropriate supported authentication method can be selected for that interface rather than assuming that every user must confirm through an email link.

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
2. Build a single-page public chat interface.
3. Add a server-side AI request handler.
4. Retrieve approved business context.
5. Require the model to flag unknowns.
6. Add human escalation.
7. If needed, add a separately authenticated owner/admin area.
8. Run a fixed evaluation set.

### Prototype evaluation
Test 20 representative questions: known-answer, missing-information, and ambiguous/adversarial cases. The assistant should answer known facts and refuse or escalate missing information without fabricating prices, hours, addresses, or availability.

## Evidence / sources used
- Supabase official authentication documentation describes multiple supported authentication approaches, including password-based, passwordless, OAuth/social, and other methods.
- Supabase documentation supports using authentication for protected application functionality; public customer FAQ access does not inherently require an authenticated user.

## Assumptions and uncertainties
- This is a prototype architecture, not a production security design.
- Exact authentication choice for a future admin area depends on product requirements.
- Exact AI model and deployment configuration are deferred.

## Unresolved issues
- Define the production data schema and monitoring controls.
