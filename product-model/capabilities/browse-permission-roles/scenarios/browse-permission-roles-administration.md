---
{
  "kind": "primary",
  "routes": {
    "web": "Administration browser"
  },
  "steps": [
    {
      "text": "The Administrator opens a selected permission-class role list.",
      "kind": "actor",
      "actor": "administrator",
      "entities": [],
      "contexts": {
        "web": {
          "place": "forum-web::administration::permission-roles"
        }
      }
    },
    {
      "text": "Definitions and order are displayed for that class.",
      "kind": "product",
      "actor": "administrator",
      "entities": [
        {
          "entity": "permission-role",
          "effect": "reads",
          "facts": [
            "Name",
            "Description",
            "Permission class",
            "Settings",
            "Order"
          ]
        }
      ],
      "contexts": {
        "web": {
          "place": "forum-web::administration::permission-roles"
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

# Browse permission roles — administration

## Trigger

The administrator opens a selected permission-class role list.

## Outcome

Definitions and order are displayed for that class.
