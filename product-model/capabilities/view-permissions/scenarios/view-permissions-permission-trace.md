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
      "text": "The administrator requests the selected registered identity option's trace.",
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
      "text": "The direct/recipient collection/role sources, membership boundaries and effective decision are displayed for the actual selected registered identity.",
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

# View permissions — permission trace

## Trigger

The administrator requests the selected account option's trace.

## Outcome

The direct/group/role sources, membership boundaries and effective decision are displayed for the actual selected account.
