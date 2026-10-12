---
{
  "kind": "primary",
  "routes": {
    "web": "Administration browser"
  },
  "steps": [
    {
      "text": "The Administrator follows a valid move-up or move-down link.",
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
      "text": "Selected/adjacent roles exchange order and class ordering is normalized.",
      "kind": "product",
      "actor": "administrator",
      "entities": [
        {
          "entity": "permission-role",
          "effect": "changes",
          "facts": [
            "Order"
          ],
          "as": "selected-role"
        },
        {
          "entity": "permission-role",
          "effect": "changes",
          "facts": [
            "Order"
          ],
          "as": "adjacent-role"
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

# Move permission role — administration

## Trigger

The administrator follows a valid move-up or move-down link.

## Outcome

Selected/adjacent roles exchange order and class ordering is normalized.
