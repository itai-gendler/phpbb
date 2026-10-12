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
      "text": "The supplied mark-read link/form proof is invalid.",
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
      "text": "The invalid-proof result is displayed without marking the requested entries.",
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

# Mark notifications read — invalid proof

## Trigger

The supplied mark-read link/form proof is invalid.

## Outcome

The invalid-proof result is displayed without marking the requested entries.
