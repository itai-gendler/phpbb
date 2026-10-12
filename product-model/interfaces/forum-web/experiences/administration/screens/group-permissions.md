---
{
  "entities": [
    {
      "entity": "user-permissions",
      "shows": [
        "Account",
        "Scope",
        "Permission class",
        "Settings",
        "Permission role"
      ]
    },
    {
      "entity": "group-permissions",
      "shows": [
        "Group",
        "Scope",
        "Permission class",
        "Settings",
        "Permission role"
      ],
      "collects": [
        "Settings",
        "Permission role"
      ]
    },
    {
      "entity": "permission-role",
      "shows": [
        "Name",
        "Description",
        "Permission class",
        "Settings",
        "Order"
      ]
    },
    {
      "entity": "group-membership",
      "shows": [
        "Account",
        "Group"
      ]
    },
    {
      "entity": "account",
      "shows": [
        "Username"
      ]
    },
    {
      "entity": "group",
      "shows": [
        "Name",
        "Type"
      ]
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
  ],
  "entryPoints": [
    {
      "forum-web": "adm/index.php?i=permissions&mode=setting_group_global"
    }
  ]
}
---

# Group permissions

The working context for group permissions. Displayed facts follow their disclosure rules. Collected input does not disclose stored credential or proof verifiers.
