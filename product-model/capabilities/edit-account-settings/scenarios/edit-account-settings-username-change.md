---
{
  "kind": "primary",
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
      "text": "The registered identity holder submits a valid replacement username and current password proof.",
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
      "text": "The account Username is changed; retained topic author/last-contribution names and forum last-contribution names are synchronized for that identity.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "account",
          "effect": "changes",
          "facts": [
            "Username"
          ]
        },
        {
          "entity": "topic",
          "effect": "changes",
          "facts": [
            "Author",
            "Last contribution"
          ]
        },
        {
          "entity": "forum",
          "effect": "changes",
          "facts": [
            "Last contribution"
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
      "target": "phpBB/includes/ucp/ucp_profile.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/includes/functions_user.php#user_update_name"
    }
  ]
}
---

# Edit account settings — username change

## Trigger

The account holder submits a valid replacement username and current password proof.

## Outcome

Username is changed and related author/name synchronization runs; unchanged fields remain unchanged.
