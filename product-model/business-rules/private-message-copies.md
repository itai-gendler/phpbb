---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "private-message"
    },
    {
      "type": "entity",
      "id": "message-copy"
    },
    {
      "type": "entity",
      "id": "account"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/includes/functions_privmsgs.php#submit_pm"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/includes/functions_privmsgs.php#delete_pm"
    }
  ]
}
---

# Mailbox copies retain separate status and sender retraction affects shared content

One shared Private message has separate Message copies for sender and recipients; Folder, New, Unread and Deleted are copy facts, not shared content status. Sending creates the sender Outbox copy and recipient copies awaiting placement. Reading an admitted unread available copy clears that copy’s Unread flag and updates the owner’s unread counter once. New-message placement is a separate effect. Deleting an ordinary available copy removes only that copy while other copies exist; after the final copy is removed, shared content and its bound files are removed. Sender Outbox deletion uses retraction: shared content is cleared and recipient copies carry Deleted so their attempted viewing returns to the mailbox. Held copies remain outside ordinary viewing.
