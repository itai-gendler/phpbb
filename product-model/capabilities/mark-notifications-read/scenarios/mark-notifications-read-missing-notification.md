---
{
  "kind": "validation",
  "routes": {
    "community": "Community browser"
  },
  "steps": [
    {
      "text": "The User follows a supplied non-AJAX single-board alert read link.",
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
      "text": "The single selected board alert is absent from the registered identity-owned lookup.",
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
      "text": "The controller returns its missing/404 result and follows no destination.",
      "kind": "product",
      "actor": "user",
      "entities": [],
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

# Mark notifications read — missing notification

## Trigger

The single selected notification is absent from the account-owned lookup.

## Outcome

The controller returns its missing/404 result and follows no destination.
