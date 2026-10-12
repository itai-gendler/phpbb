---
{
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/includes/functions_privmsgs.php#write_pm_addresses"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/phpbb/auth/auth.php#acl_raw_data_single_user"
    }
  ],
  "relations": [
    {
      "entity": "group-membership",
      "verb": "contains",
      "cardinality": "one-to-many"
    },
    {
      "entity": "group-permissions",
      "verb": "contains",
      "cardinality": "one-to-many"
    }
  ]
}
---

# Group

A runtime group consulted by permissions, disclosure and message addressing.

## Information kept

- **Name** — The displayed name of this group.
- **Type** — The runtime group classification used by filtering and membership.
- **Receive private messages** — The runtime group’s receiving option.
- **Leader exemption** — The configured group-leader exemptions used in effective permission resolution.
