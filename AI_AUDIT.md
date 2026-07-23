### Feature: Webhook verification
- Classification: NEW TECH -- manual-first.
- Who wrote the code: Me.

### Feature: Payload logging middleware
- Classification: Repeated pattern (Express middleware).
- Who wrote the code: Me,.I chose manual because the file is small.

# DAY 2
No AI used


# DAY 3
## Schema (new-tech-adjacent, manual)
Wrote `db/schema.sql` by hand — three tables (`leads`, `conversations`, `messages`) 
with foreign key references and default timestamps. New to SQLite as a tool, 
but the schema design and SQL syntax were written manually.

## Phone-to-lead mapping (manual, bridge logic)
Wrote `db/leads.js` (`findOrCreateLead`, `updateLead`), `db/conversations.js` 
(`getConversation`, `saveConversation`), and `db/messages.js` (`logMessage`) by hand, 
plus the promise wrappers in `db/helpers.js` (`dbGet`, `dbRun`) to bridge the 
callback-based `sqlite3` API into async/await. Wired these into the WhatsApp 
webhook handler (`routes/whatsapp.js`) to replace the in-memory `sessions` Map 
with SQL-backed state — this is the core "glue" connecting the bot's state 
machine to persistent storage. Debugged manually (Promise mechanics, SQL syntax, 
branch logic for lead field updates) through iterative review with AI guidance, 
not AI-generated code.

## CRUD routes (AI-assisted, repeated pattern)
`GET /api/leads`, `GET /api/leads/:id`, `PATCH /api/leads/:id` — AI-generated 
per the task's explicit allowance. Standard REST CRUD pattern over the existing 
schema.

## Pagination helper (AI-assisted, repeated pattern)
Limit/offset/search/status filtering logic in `GET /api/leads` — AI-generated 
alongside the CRUD routes above, same file. Standard pagination pattern 
(clamped limit, offset, LIKE-based search, WHERE filtering).