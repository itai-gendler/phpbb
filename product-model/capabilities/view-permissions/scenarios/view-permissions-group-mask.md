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
      "text": "The administrator selects an effective recipient collection mask.",
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
      "text": "The selected recipient collection/class decisions are displayed without changing assignments.",
      "kind": "product",
      "actor": "administrator",
      "entities": [
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

# View permissions — group mask

## Trigger

The administrator selects an effective group mask.

## Outcome

The selected group/class decisions are displayed without changing assignments.
