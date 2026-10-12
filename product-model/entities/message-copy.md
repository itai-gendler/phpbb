---
{
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/includes/functions_privmsgs.php#delete_pm"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/includes/functions_privmsgs.php#update_unread_status"
    }
  ]
}
---

# Message copy

One account’s mailbox status for a shared private message.

## Information kept

- **Owner** — The account whose mailbox holds this copy.
- **Message** — The shared content associated with this account’s mailbox copy.
- **Folder** — The copy’s mailbox destination, including Outbox, Inbox, no-box and Held distinctions.
- **New** — Whether the mailbox copy is still new for its owner.
- **Unread** — Whether the mailbox copy remains unread for its owner.
- **Deleted** — Whether the mailbox copy refers to retracted content.

## States

### Awaiting placement

The recipient copy is new and has not reached an ordinary folder.

### Available

The copy is placed in an accessible mailbox folder.

### Held

The copy is held outside ordinary viewing.

### Deleted

The item is retained in its deleted classification.
