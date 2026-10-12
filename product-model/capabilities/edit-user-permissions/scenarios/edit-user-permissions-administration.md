---
{
  "kind": "primary",
  "routes": {
    "web": "Administration browser"
  },
  "steps": [
    {
      "text": "The Administrator submits accepted global registered identity assignment changes.",
      "kind": "actor",
      "actor": "administrator",
      "entities": [],
      "contexts": {
        "web": {
          "place": "forum-web::administration::user-permissions"
        }
      }
    },
    {
      "text": "Selected settings/role assignments are replaced and effective caches refreshed.",
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
        }
      ],
      "contexts": {
        "web": {
          "place": "forum-web::administration::user-permissions"
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

# Edit user permissions — administration

## Trigger

The administrator submits accepted global account assignment changes.

## Outcome

Selected settings/role assignments are replaced and effective caches refreshed.
