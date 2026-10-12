---
{
  "entities": [
    {
      "entity": "account",
      "collects": [
        "Username",
        "Email",
        "Credential",
        "Preferred language",
        "Timezone",
        "Profile values"
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/includes/ucp/ucp_register.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/includes/functions_user.php#user_add"
    }
  ],
  "entryPoints": [
    {
      "forum-web": "ucp.php?mode=register"
    }
  ]
}
---

# Registration

The working context for registration. Displayed facts follow their disclosure rules. Collected input does not disclose stored credential or proof verifiers.
