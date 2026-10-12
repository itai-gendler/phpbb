---
{
  "kind": "primary",
  "routes": {
    "web": "Community browser"
  },
  "steps": [
    {
      "text": "The User opens board alert.",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "web": {
          "place": "forum-web::community::notifications"
        }
      }
    },
    {
      "text": "The board method displays this registered identity's enabled-type notifications and computes unread totals.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "notification",
          "effect": "reads",
          "facts": [
            "Event",
            "Origin",
            "Destination",
            "Created at",
            "Read status",
            "Display information"
          ]
        }
      ],
      "contexts": {
        "web": {
          "place": "forum-web::community::notifications"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/includes/ucp/ucp_notifications.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/phpbb/notification/method/board.php"
    }
  ]
}
---

# Browse notifications — community

## Trigger

The account holder opens Notifications.

## Outcome

The board method displays this account's enabled-type notifications and computes unread totals.
