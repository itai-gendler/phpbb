---
{
  "kind": "primary",
  "routes": {
    "community": "Community browser"
  },
  "steps": [
    {
      "text": "The User confirms removal from the Outbox while recipient copies await placement.",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "community": {
          "place": "forum-web::community::private-message"
        }
      }
    },
    {
      "text": "The sender confirms removal of the Outbox copy while recipient copies remain.",
      "kind": "condition",
      "actor": "user",
      "entities": [],
      "contexts": {
        "community": {
          "place": "forum-web::community::private-message"
        }
      }
    },
    {
      "text": "The sender copy is removed, shared content becomes Retracted and remaining copies are flagged Deleted; corresponding counters/notifications are maintained.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "message-copy",
          "effect": "removes",
          "as": "sender-copy",
          "from": "Available"
        },
        {
          "entity": "private-message",
          "effect": "changes",
          "facts": [
            "Content"
          ],
          "to": "Retracted",
          "from": "Sent"
        },
        {
          "entity": "message-copy",
          "effect": "changes",
          "as": "recipient-copy",
          "facts": [
            "Deleted"
          ],
          "to": "Deleted",
          "from": "Awaiting placement"
        },
        {
          "entity": "notification",
          "effect": "removes",
          "from": "Unread"
        }
      ],
      "contexts": {
        "community": {
          "place": "forum-web::community::private-message"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/includes/functions_privmsgs.php#delete_pm"
    }
  ]
}
---

# Delete private message — outbox retraction

## Trigger

The sender confirms removal of the Outbox copy while recipient copies remain.

## Outcome

The sender copy is removed, shared content becomes Retracted and remaining copies are flagged Deleted; corresponding counters/notifications are maintained.

## Edge cases

- A sender Outbox copy has no owner new/unread contribution to decrement; recipient copies remain flagged Deleted rather than being removed.
