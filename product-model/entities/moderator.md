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

# Moderator

A person exercising configured forum moderation authority. The role name alone grants no operation.
