---
{
  "entities": [
    {
      "entity": "permission-role",
      "shows": [
        "Name",
        "Description",
        "Permission class",
        "Settings",
        "Order"
      ],
      "collects": [
        "Name",
        "Description",
        "Permission class",
        "Settings"
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/includes/acp/acp_permission_roles.php"
    }
  ],
  "entryPoints": [
    {
      "forum-web": "adm/index.php?i=permission_roles"
    }
  ]
}
---

# Permission role

The working context for permission role. Displayed facts follow their disclosure rules. Collected input does not disclose stored credential or proof verifiers.
