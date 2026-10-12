---
{
  "kind": "validation",
  "routes": {
    "community": "Community browser"
  },
  "steps": [
    {
      "text": "The User confirms ordinary-folder copy removal while other copies remain.",
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
      "text": "No matching owned folder copy exists.",
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
      "text": "No copy is removed by the registered identity/folder-scoped request.",
      "kind": "product",
      "actor": "user",
      "entities": [],
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

# Delete private message — missing copy

## Trigger

No matching owned folder copy exists.

## Outcome

No copy is removed by the account/folder-scoped request.
