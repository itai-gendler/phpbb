---
{
  "kind": "primary",
  "routes": {
    "web": "Community browser"
  },
  "steps": [
    {
      "text": "The User follows a valid non-AJAX single-board alert read link.",
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
      "text": "The Product consults notification Read status",
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
        "web": {
          "place": "forum-web::community::notifications"
        }
      }
    },
    {
      "text": "The selected notification becomes Read and completion follows its stored destination.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "notification",
          "effect": "reads",
          "facts": [
            "Destination"
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

# Mark notifications read — community

## Trigger

The account holder follows a valid non-AJAX single-notification read link.

## Outcome

The selected notification becomes Read and completion follows its stored destination.
