---
{
  "kind": "primary",
  "routes": {
    "web": "Administration browser"
  },
  "steps": [
    {
      "text": "The Administrator confirms removal of a selected role.",
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
      "text": "Assigned settings are materialized into direct assignments before the role is removed; caches refresh.",
      "kind": "product",
      "actor": "administrator",
      "entities": [
        {
          "entity": "user-permissions",
          "effect": "changes",
          "facts": [
            "Settings",
            "Permission role"
          ]
        },
        {
          "entity": "group-permissions",
          "effect": "changes",
          "facts": [
            "Settings",
            "Permission role"
          ]
        },
        {
          "entity": "permission-role",
          "effect": "removes"
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

# Delete permission role — administration

## Trigger

The administrator confirms removal of a selected role.

## Outcome

Assigned settings are materialized into direct assignments before the role is removed; caches refresh.
