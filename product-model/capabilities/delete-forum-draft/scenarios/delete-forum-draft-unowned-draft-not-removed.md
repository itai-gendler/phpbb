---
{
  "kind": "validation",
  "routes": {
    "community": "Community browser"
  },
  "steps": [
    {
      "text": "The User submits selected draft removal with a supplied form.",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "community": {
          "place": "forum-web::community::drafts"
        }
      }
    },
    {
      "text": "The selected identifier belongs to another registered identity.",
      "kind": "condition",
      "actor": "user",
      "entities": [],
      "contexts": {
        "community": {
          "place": "forum-web::community::drafts"
        }
      }
    },
    {
      "text": "The registered identity-scoped deletion does not remove that draft.",
      "kind": "product",
      "actor": "user",
      "entities": [],
      "contexts": {
        "community": {
          "place": "forum-web::community::drafts"
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

# Delete forum draft — unowned draft not removed

## Trigger

The selected identifier belongs to another account.

## Outcome

The account-scoped deletion does not remove that draft.
