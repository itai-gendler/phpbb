---
{
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/includes/acp/auth.php#acl_set"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/phpbb/auth/auth.php#acl_raw_data_single_user"
    }
  ]
}
---

# Group permissions

A separately editable assignment to a group in a global or forum scope.

## Information kept

- **Group** — The selected runtime group.
- **Scope** — The global or selected forum scope of the assignment.
- **Permission class** — The administrative, user, moderator or forum permission class.
- **Settings** — The permission options and their Yes/No/Never decisions.
- **Permission role** — The reusable definition supplying the assignment’s settings, if selected.
