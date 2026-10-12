---
{
  "kind": "primary",
  "routes": {
    "community": "Community browser"
  },
  "steps": [
    {
      "text": "The User submits selected read-status marks with the form token.",
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
      "text": "The registered identity holder submits selected IDs with valid form input.",
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
      "text": "Matching registered identity-owned notifications become Read; other recipients' entries are unchanged.",
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

# Mark notifications read — selected notifications

## Trigger

The account holder submits selected IDs with valid form input.

## Outcome

Matching account-owned notifications become Read; other recipients' entries are unchanged.
