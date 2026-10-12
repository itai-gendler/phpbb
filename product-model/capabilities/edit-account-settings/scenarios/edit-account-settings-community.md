---
{
  "kind": "primary",
  "routes": {
    "web": "Community browser"
  },
  "steps": [
    {
      "text": "The User supplies the current password and matching valid replacement on Edit account settings.",
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
        "web": {
          "place": "forum-web::community::account"
        }
      }
    },
    {
      "text": "The credential and its change time are saved and remembered login keys reset.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "account",
          "effect": "changes",
          "facts": [
            "Credential",
            "Credential changed at"
          ]
        }
      ],
      "contexts": {
        "web": {
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

# Edit account settings — community

## Trigger

The account holder supplies the current password and matching valid replacement on Edit account settings.

## Outcome

The credential and its change time are saved and remembered login keys reset.
