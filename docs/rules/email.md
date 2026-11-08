# Email rules

## Forwarded client emails (how clients arrive)

Client emails reach her personal Gmail forwarded from her work address, with a subject
starting `Fw:`. So the Gmail sender is always her own work address and says nothing about
the client.

- The client is whoever wrote the **original** message: the `From:` line in the forwarded
  block in the body (name and email). Match that person to the Client index.
- Ignore `Fw:` in the subject. The original subject is in the forwarded block.
- The original text may be empty and only have attachments. Match by the original sender
  and use the attachment names.
- A forward is only a client email if it has a forwarded block. Anything else from her
  work address is "other".
- Automated lender or insurer emails are not forwards. Match them on the surname or
  reference in the text.
- Never reply to her work address as if it were the client. A draft goes to the original
  sender's address.
- The `Client/<ID> <name>` label goes on the forwarded thread. The Apps Script works from
  the label, so attachments are saved from forwards too.

## Triage ("triage my inbox")

1. Look at unread emails since the last triage (or the last 24 hours).
2. For each email, decide what it is:
   - new enquiry
   - documents from a client
   - lender or insurer update
   - meeting request or change
   - other (newsletters, marketing: skip, don't list)
3. Match it to a client by the original sender (see above). If it matches a client, apply
   that client's label.
   If it's a new person, list it as a possible new client and ask her.
4. Update the case file (see `../workflow/case-file.md`). Then mark the email as read.
5. Where a reply is needed, don't draft it yet. List it as a proposal (see below).
6. Finish with a short list: what you did, replies you propose to draft, what needs her decision,
   and any stuck cases.

## Drafting replies

- **Confirm first.** Before creating a draft, tell her in one or two lines who it's to and
  what it would say, then wait. She can say yes, change it, or skip it. "Yes to all" covers
  every proposal in that list.
- Drafts only. Never send.
- Read `Assistant preferences` in her Drive first for tone and signature.
- Short and friendly. Say what you received and what's still needed, with a list if more
  than two items.
- Don't give advice on products, rates or affordability in a draft. That's her job and
  it's regulated. Write "I'll come back to you on this" and flag it to her.
- Don't promise dates that depend on a lender.
- Never paste a client's personal details into a reply to someone else.

## Attachments

You can see attachment names, not their content. The Apps Script saves the files to Drive.
Use the names and the email text to tick documents (see
`../workflow/document-checklists.md`).
