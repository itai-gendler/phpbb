---
{
  "kind": "primary",
  "routes": {
    "web": "Administration browser"
  },
  "steps": [
    {
      "text": "The Administrator submits global recipient collection permission options or an applicable role.",
      "kind": "actor",
      "actor": "administrator",
      "entities": [],
      "contexts": {
        "web": {
          "place": "forum-web::administration::group-permissions"
        }
      }
    },
    {
      "text": "recipient collection assignments are created and effective caches and applicable reviewing person information refreshed.",
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
        "web": {
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

# Add group permissions — administration

## Trigger

The administrator submits global group permission options or an applicable role.

## Outcome

Group assignments are created and effective caches and applicable moderator information refreshed.
