---
{
  "kind": "primary",
  "routes": {
    "web": "Administration browser"
  },
  "steps": [
    {
      "text": "The Administrator confirms selected global registered identity assignment removal.",
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
      "text": "Assignments are removed and effective caches cleared.",
      "kind": "product",
      "actor": "administrator",
      "entities": [
        {
          "entity": "user-permissions",
          "effect": "removes"
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

# Remove user permissions — administration

## Trigger

The administrator confirms selected global account assignment removal.

## Outcome

Assignments are removed and effective caches cleared.
