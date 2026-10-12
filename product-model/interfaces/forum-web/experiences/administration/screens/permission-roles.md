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

# Permission roles

The working context for permission roles. Displayed facts follow their disclosure rules. Collected input does not disclose stored credential or proof verifiers.
