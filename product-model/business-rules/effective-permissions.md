---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "user-permissions"
    },
    {
      "type": "entity",
      "id": "group-permissions"
    },
    {
      "type": "entity",
      "id": "permission-role"
    },
    {
      "type": "entity",
      "id": "group-membership"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/phpbb/auth/auth.php#acl_get"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/phpbb/auth/auth.php#acl_cache"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/phpbb/auth/auth.php#acl_raw_data_single_user"
    }
  ]
}
---

# Effective permissions combine the actual direct, role and group decisions

resolve direct and eligible group authority; exclude pending membership and configured leader exemptions; preserve Never handling and global/local combination; Founder forces administrative options only.

## Resolution

Resolve the actual account and forum/global scope. Direct entries and assigned role settings are combined with eligible nonpending memberships and their group entries. Preserve ACL_NEVER precedence and the configured group-leader exemptions in acl_raw_data_single_user. acl_get combines a global/local option with OR when a forum is supplied. acl_cache forces only global administrative a_* options for Founder; it does not force moderator, forum or user options.
