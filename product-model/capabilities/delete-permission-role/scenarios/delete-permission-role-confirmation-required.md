---
{
  "kind": "primary",
  "routes": {
    "administration": "Administration browser"
  },
  "steps": [
    {
      "text": "The Administrator requests removal of the selected entries.",
      "kind": "actor",
      "actor": "administrator",
      "entities": [],
      "contexts": {
        "administration": {
          "place": "forum-web::administration::permission-role"
        }
      }
    },
    {
      "text": "The role removal request has not yet confirmed its selection.",
      "kind": "condition",
      "actor": "administrator",
      "entities": [],
      "contexts": {
        "administration": {
          "place": "forum-web::administration::permission-role"
        }
      }
    },
    {
      "text": "The Product requests confirmation; valid confirmation materializes assignments and removes the selected role.",
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
        "administration": {
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

# Delete permission role — confirmation required

## Trigger

The role removal request has not yet confirmed its selection.

## Outcome

The Product requests confirmation; valid confirmation materializes assignments and removes the selected role.
