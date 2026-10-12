---
{
  "actors": [
    "user"
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/viewtopic.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/phpbb/content_visibility.php#is_visible"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/includes/ucp/ucp_profile.php"
    }
  ]
}
---

# Change required account password

## Goal

Complete the credential change required while entering a discussion.

## Success criterion

The account holder reaches Edit account settings through the interception and saves a valid replacement.
