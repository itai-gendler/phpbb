---
{
  "kind": "primary",
  "routes": {
    "web": "Administration browser"
  },
  "steps": [
    {
      "text": "The Administrator submits a unique name, bounded description, nonempty class settings and valid form.",
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
      "text": "The role header is inserted at the end of its class and settings stored.",
      "kind": "product",
      "actor": "administrator",
      "entities": [
        {
          "entity": "permission-role",
          "effect": "creates",
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

# Create permission role — administration

## Trigger

The administrator submits a unique name, bounded description, nonempty class settings and valid form.

## Outcome

The role header is inserted at the end of its class and settings stored.
