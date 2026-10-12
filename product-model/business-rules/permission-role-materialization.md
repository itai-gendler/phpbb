---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "permission-role"
    },
    {
      "type": "entity",
      "id": "user-permissions"
    },
    {
      "type": "entity",
      "id": "group-permissions"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/includes/acp/acp_permission_roles.php#remove_role"
    }
  ]
}
---

# Role removal materializes its assigned settings

Before removing a Permission role, the remove_role path copies the role’s option values into direct settings for its assigned User permissions and Group permissions, clears their role reference, then removes role data/header and invalidates effective permission caches. Deleting a role therefore does not silently discard the permissions it had supplied to those assignments.
