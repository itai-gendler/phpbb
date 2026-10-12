---
{
  "kind": "primary",
  "routes": {
    "community": "Community browser"
  },
  "steps": [
    {
      "text": "The User follows the mark-all read-status link with its token and cutoff.",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "community": {
          "place": "forum-web::community::notifications"
        }
      }
    },
    {
      "text": "The registered identity holder follows a valid mark-all link with its form-time cutoff.",
      "kind": "condition",
      "actor": "user",
      "entities": [],
      "contexts": {
        "community": {
          "place": "forum-web::community::notifications"
        }
      }
    },
    {
      "text": "The registered identity's notifications up to the cutoff become Read; later entries are not swept into that request.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "notification",
          "effect": "changes",
          "facts": [
            "Read status"
          ],
          "from": "Unread",
          "to": "Read"
        }
      ],
      "contexts": {
        "community": {
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

# Mark notifications read — all notifications

## Trigger

The account holder follows a valid mark-all link with its form-time cutoff.

## Outcome

The account's notifications up to the cutoff become Read; later entries are not swept into that request.
