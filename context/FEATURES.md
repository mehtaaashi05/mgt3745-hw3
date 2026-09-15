# Features and specification

## Context
An intern on one team becomes curious about another and wants firsthand information before deciding whether to pursue a move, without signaling dissatisfaction or requesting a transfer.

## Users
Profiles and evidence in USERS.md: PROFILE-01 (The Hesitant Explorer), who is curious about another team but has not done anything about it and PROFILE-02 (The Proactive Outreacher), who shows a receptive contact can be reached without an existing connection.

## Scope
Covers requesting and completing one short, informal, no-commitment conversation with someone from a different team, visible to the intern's current manager and framed as standard program participation with an explicit no-standing-impact guarantee.

Does not cover: formal transfer/rotation applications, scheduling automation beyond one request/response, performance or return-offer decisions, or full-time employees (interns only).

### Kano hypotheses

| Feature ID | Feature | Kano hypothesis | Segment / date | Evidence and reasoning |
|---|---|---|---|---|
| F-01 |Opt-in directory of employees willing to have a 15-20 minute informal conversation with an intern from another team.  |Must-be |Both segments - Sept 08 |NT-02 succeeded via self-arranged cold outreach; INT-01 confirmed no formal way exists to find who's approachable. |
| F-02 |Explicit "Information only/no commitment" framing on every conversation request |Performance |Hesitant Explorer - Sept 08 |INT-01: "tell me about your team" felt far less risky than "I want to move." |
| F-03 |Current manager notified when a cross-team conversation happens, framed as standard program participation with an explicit no-standing-imapct gurantee |Performance |Hesitant Explorer - Sept 08 |INT-02's manager reacted "pretty positively," challenging that visibility itself is the risk. |
| F-04 |Static content pages of typical work per line of business |Indifferent |Both segments - Sept 08 |Already exists informally; INT-02 says shadowing, not reading, confirmed his interest. |
| F-05 |Formal application required just to start an exploratory conversation |Reverse |Both segments - Sept 08 |Both interviews show the value came from low-commitment, informal contact. Requiring paperwork to even start exploring would reintroduce the friction. |
| F-06 |Anonymized visibility into how many interns have completed exploratory conversations |Attractive |Both segments - Sept 08 |Targets the perceived-vs-actual risk gap by normalizing exploration. |


## Behavior
1. WHEN an intern views the directory, THE SYSTEM SHALL show only opted-in employees.
WHEN a request is submitted, THE SYSTEM SHALL label it informational and non-committal to the recipient.
2. WHEN a request is submitted, THE SYSTEM SHALL notify the intern's manager, framed as standard participation.
3. WHEN a request is accepted, THE SYSTEM SHALL let both parties schedule within 5 business days.
4. IF an employee doesn't respond within 3 business days, THEN THE SYSTEM SHALL notify the intern and allow selecting someone else.
5. WHILE an internship is active, THE SYSTEM SHALL allow requests to more than one line of business.
6. IF the internship end date passes, THEN THE SYSTEM SHALL disable new requests.

## Constraints
- Only current employees and interns of the organization may access the directory; the system must sit behind existing internal authentication.
- An employee's opt-in status must be self-managed and revocable at any time.
- The organization must commit that a cross-team conversation request carries no negative weight in an intern's performance review or return-offer decision; this guarantee must be visible to the intern before they submit a request.
- The organization must make it clear to the intern and team that this is not a formal request for transfer.
- The system must retain no conversation content, only the fact that a request was made and its status.

## Acceptance
- WHEN a request is submitted, THE SYSTEM SHALL confirm within 2 seconds.
- WHEN an intern completes two conversations, THE SYSTEM SHALL show the manager was notified of both and no negative flag was recorded.
- WHEN an employee opts out, THE SYSTEM SHALL remove them from results within 1 minute.
- WHEN the internship ends, THE SYSTEM SHALL disable new requests by the next day.
- WHEN an exploratory request completes, THE SYSTEM SHALL NOT create a transfer request.

## Handoff reflection
Still open: who decides which employees can opt in; what happens if requests exceed the volunteer pool; whether this stays pilot-scoped to one division; and what enforces the no-standing-impact guarantee beyond stating it.

## AI assistance
I used AI to make sure I met all the requirements by running my entry through Copilot and having it compare my assignment to the rubric.

## Verification

- WHEN a request is submitted, THE SYSTEM SHALL confirm within 2 seconds. PASS. When an intern clicks on "Request a conversation", a message saying "Conversation request sent. This is informational and non-committal pops up."
- WHEN an intern completes two conversations, THE SYSTEM SHALL show the manager was notified of both and no negative flag was recorded. CANNOT TEST YET. This build only implements F-01, the directory; There is no system in place to enforce the manager notifications yet. That will be a later addition.
- WHEN an employee opts out, THE SYSTEM SHALL remove them from results within 1 minute. PASS. Clicking "Opt out" removes the entry and re-renders the list immediately — well under the 1-minute bound.
- WHEN the internship ends, THE SYSTEM SHALL disable new requests by the next day. DEFERRED. see ADR-001. I will implement this in the next round. 
- WHEN an exploratory request completes, THE SYSTEM SHALL NOT create a transfer request. CANNOT TEST YET. Since this feature is about the directory, it does not have anything regarding post conversation. There is no system in place yet about what happens once a conversation occurs. 
