---
{
  "kind": "validation",
  "routes": {
    "community": "Community browser"
  },
  "steps": [
    {
      "text": "The User supplies the current password and entered replacement on Edit account settings.",
      "kind": "actor",
      "actor": "user",
      "entities": [
        {
          "entity": "account",
          "effect": "reads",
          "facts": [
            "Username"
          ]
        }
      ],
      "contexts": {
        "community": {
          "place": "forum-web::community::account"
        }
      }
    },
    {
      "text": "A proposed username reaches the retained-field branch.",
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
      "text": "The existing username remains; the submitted change is not persisted.",
      "kind": "product",
      "actor": "user",
      "entities": [],
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
      "target": "phpBB/includes/ucp/ucp_profile.php"
    }
  ]
}
---

# Edit account settings — name retained

## Trigger

A proposed username reaches the retained-field branch.

## Outcome

The existing username remains; the submitted change is not persisted.
