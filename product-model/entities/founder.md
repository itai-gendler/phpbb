---
{
  "acts": "external",
  "kind": "person",
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/phpbb/auth/auth.php#acl_cache"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/includes/functions.php#login_box"
    }
  ],
  "relations": [
    {
      "entity": "account",
      "verb": "owns",
      "cardinality": "one-to-one"
    }
  ]
}
---

# Founder

A founder account. The shipped override forces administrative options, not every forum or moderator permission.
