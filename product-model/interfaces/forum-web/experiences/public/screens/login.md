---
{
  "entities": [
    {
      "entity": "account",
      "collects": [
        "Username",
        "Credential"
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/ucp.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/includes/functions.php#login_box"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/phpbb/auth/provider/db.php#login"
    }
  ],
  "entryPoints": [
    {
      "forum-web": "ucp.php?mode=login"
    }
  ]
}
---

# Login

The working context for login. Displayed facts follow their disclosure rules. Collected input does not disclose stored credential or proof verifiers.
