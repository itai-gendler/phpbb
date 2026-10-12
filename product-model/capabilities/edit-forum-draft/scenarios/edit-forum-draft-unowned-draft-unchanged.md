---
{
  "kind": "validation",
  "routes": {
    "community": "Community browser"
  },
  "steps": [
    {
      "text": "The User submits a nonempty subject/content for a selected draft.",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "community": {
          "place": "forum-web::community::draft"
        }
      }
    },
    {
      "text": "The supplied selected identifier belongs to another registered identity.",
      "kind": "condition",
      "actor": "user",
      "entities": [],
      "contexts": {
        "community": {
          "place": "forum-web::community::draft"
        }
      }
    },
    {
      "text": "That draft is not changed by the registered identity-scoped update.",
      "kind": "product",
      "actor": "user",
      "entities": [],
      "contexts": {
        "community": {
          "place": "forum-web::community::draft"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/includes/ucp/ucp_main.php"
    }
  ]
}
---

# Edit forum draft — unowned draft unchanged

## Trigger

The supplied selected identifier belongs to another account.

## Outcome

That draft is not changed by the account-scoped update.
