---
{
  "kind": "primary",
  "routes": {
    "administration": "Administration browser"
  },
  "steps": [
    {
      "text": "The Administrator submits global recipient collection permission options or an applicable role.",
      "kind": "actor",
      "actor": "administrator",
      "entities": [],
      "contexts": {
        "administration": {
          "place": "forum-web::administration::group-permissions"
        }
      }
    },
    {
      "text": "The administrator selects valid subjects and a posting area-local permission class/scope.",
      "kind": "condition",
      "actor": "administrator",
      "entities": [],
      "contexts": {
        "administration": {
          "place": "forum-web::administration::group-permissions"
        }
      }
    },
    {
      "text": "The selected posting area-scoped assignments follow the requested operation; global assignments outside that selection remain.",
      "kind": "product",
      "actor": "administrator",
      "entities": [
        {
          "entity": "group-permissions",
          "effect": "creates",
          "facts": [
            "Group",
            "Scope",
            "Permission class",
            "Settings",
            "Permission role"
          ]
        }
      ],
      "contexts": {
        "administration": {
          "place": "forum-web::administration::group-permissions"
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

# Add group permissions — forum scope

## Trigger

The administrator selects valid subjects and a forum-local permission class/scope.

## Outcome

The selected forum-scoped assignments follow the requested operation; global assignments outside that selection remain.
