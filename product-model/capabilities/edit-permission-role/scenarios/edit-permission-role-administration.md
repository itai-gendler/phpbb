---
{
  "kind": "primary",
  "routes": {
    "web": "Administration browser"
  },
  "steps": [
    {
      "text": "The Administrator submits a valid selected role definition and class settings.",
      "kind": "actor",
      "actor": "administrator",
      "entities": [],
      "contexts": {
        "web": {
          "place": "forum-web::administration::permission-role"
        }
      }
    },
    {
      "text": "The header/settings are saved and applicable caches refreshed.",
      "kind": "product",
      "actor": "administrator",
      "entities": [
        {
          "entity": "permission-role",
          "effect": "changes",
          "facts": [
            "Name",
            "Description",
            "Settings"
          ]
        }
      ],
      "contexts": {
        "web": {
          "place": "forum-web::administration::permission-role"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/includes/acp/acp_permission_roles.php"
    }
  ]
}
---

# Edit permission role — administration

## Trigger

The administrator submits a valid selected role definition and class settings.

## Outcome

The header/settings are saved and applicable caches refreshed.
