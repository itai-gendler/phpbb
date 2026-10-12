---
{
  "kind": "primary",
  "routes": {
    "administration": "Administration browser"
  },
  "steps": [
    {
      "text": "The Administrator requests an registered identity's effective global mask.",
      "kind": "actor",
      "actor": "administrator",
      "entities": [],
      "contexts": {
        "administration": {
          "place": "forum-web::administration::permission-masks"
        }
      }
    },
    {
      "text": "The administrator selects a posting area-local permission mask.",
      "kind": "condition",
      "actor": "administrator",
      "entities": [],
      "contexts": {
        "administration": {
          "place": "forum-web::administration::permission-masks"
        }
      }
    },
    {
      "text": "The selected posting area-scope decisions are displayed rather than global-only decisions.",
      "kind": "product",
      "actor": "administrator",
      "entities": [
        {
          "entity": "user-permissions",
          "effect": "reads",
          "facts": [
            "Account",
            "Scope",
            "Permission class",
            "Settings",
            "Permission role"
          ]
        },
        {
          "entity": "group-permissions",
          "effect": "reads",
          "facts": [
            "Group",
            "Scope",
            "Permission class",
            "Settings",
            "Permission role"
          ]
        },
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
        },
        {
          "entity": "group-membership",
          "effect": "reads",
          "facts": [
            "Account",
            "Group",
            "Pending",
            "Leader",
            "Default"
          ]
        }
      ],
      "contexts": {
        "administration": {
          "place": "forum-web::administration::permission-masks"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/includes/acp/acp_permissions.php#set_permissions"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/includes/acp/auth.php#acl_set"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/includes/acp/auth.php#acl_delete"
    }
  ]
}
---

# View permissions — forum mask

## Trigger

The administrator selects a forum-local permission mask.

## Outcome

The selected forum-scope decisions are displayed rather than global-only decisions.
