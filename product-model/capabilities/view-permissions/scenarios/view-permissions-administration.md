---
{
  "kind": "primary",
  "routes": {
    "web": "Administration browser"
  },
  "steps": [
    {
      "text": "The Administrator requests an registered identity's effective global mask.",
      "kind": "actor",
      "actor": "administrator",
      "entities": [],
      "contexts": {
        "web": {
          "place": "forum-web::administration::permission-masks"
        }
      }
    },
    {
      "text": "The selected class/registered identity mask is displayed without changing assignments.",
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
        "web": {
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

# View permissions — administration

## Trigger

The administrator requests an account's effective global mask.

## Outcome

The selected class/account mask is displayed without changing assignments.
