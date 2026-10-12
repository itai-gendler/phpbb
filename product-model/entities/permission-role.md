---
{
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/includes/acp/acp_permission_roles.php"
    }
  ],
  "relations": [
    {
      "entity": "user-permissions",
      "verb": "is assigned to",
      "cardinality": "one-to-many"
    },
    {
      "entity": "group-permissions",
      "verb": "is assigned to",
      "cardinality": "one-to-many"
    }
  ]
}
---

# Permission role

A reusable, ordered permission definition for one permission class.

## Information kept

- **Name** — The displayed name of this permission role.
- **Description** — The kept descriptive text.
- **Permission class** — The administrative, user, moderator or forum permission class.
- **Settings** — The permission options and their Yes/No/Never decisions.
- **Order** — The relative position within the permission class.
