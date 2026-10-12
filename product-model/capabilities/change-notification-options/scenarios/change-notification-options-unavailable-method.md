---
{
  "kind": "primary",
  "routes": {
    "community": "Community browser"
  },
  "steps": [
    {
      "text": "The User submits board alert type and method choices.",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "community": {
          "place": "forum-web::community::account"
        }
      }
    },
    {
      "text": "A board alert type or method is unavailable to this options process.",
      "kind": "condition",
      "actor": "user",
      "entities": [],
      "contexts": {
        "community": {
          "place": "forum-web::community::account"
        }
      }
    },
    {
      "text": "The unavailable choice is not offered as usable; the applicable choices follow their add/remove subscription behavior.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "account",
          "effect": "changes",
          "facts": [
            "Notification choices"
          ]
        }
      ],
      "contexts": {
        "community": {
          "place": "forum-web::community::account"
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

# Change notification options — unavailable method

## Trigger

A notification type or method is unavailable to this options process.

## Outcome

The unavailable choice is not offered as usable; the applicable choices follow their add/remove subscription behavior.
