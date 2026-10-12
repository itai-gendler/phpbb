---
{
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/includes/functions_privmsgs.php#submit_pm"
    }
  ],
  "relations": [
    {
      "entity": "attachment",
      "verb": "contains",
      "cardinality": "one-to-many"
    },
    {
      "entity": "message-copy",
      "verb": "contains",
      "cardinality": "one-to-many"
    }
  ]
}
---

# Private message

Shared message content and addressing, separate from each account’s copy.

## Information kept

- **Subject** — The message subject shown in mailbox and message views.
- **Content** — The kept submitted text and its content representation.
- **Sender** — The identity that submitted the shared message.
- **To recipients** — The addressed individuals/groups, shown through the filtered address projection.
- **Blind-copy recipients** — The addressed individuals and groups; presentation filters each through sender/self/membership checks.
- **Sent at** — When the shared message was submitted.
- **Formatting choices** — The kept BBCode/link/smiley/signature choices used in presentation.
- **Edit information** — The retained editor/time/reason/count information from the applicable edit path.
- **Reply origin** — The originating message selected for the kept reply/forward relation.
- **Attachments present** — Whether this private message has bound files.

## States

### Sent

The shared message content remains present.

### Retracted

The sender’s Outbox removal has cleared the shared content and flagged remaining copies.
