---
{
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/phpbb/notification/method/board.php"
    }
  ]
}
---

# Notification

A recipient’s persisted board event and destination.

## Information kept

- **Recipient** — The account to which the notification belongs.
- **Event** — The kept notification type and item identity.
- **Origin** — The originating content/actor information carried by the event.
- **Destination** — The notification’s kept destination.
- **Created at** — When this notification was created.
- **Read status** — Whether the notification remains unread or is marked read.
- **Display information** — The event data kept for notification presentation.

## States

### Unread

The notification has not been marked read.

### Read

The notification is marked read.
