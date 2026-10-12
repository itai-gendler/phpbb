---
{
  "entities": [
    {
      "entity": "account",
      "collects": [
        "Activation proof"
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/includes/ucp/ucp_activate.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/includes/functions_user.php#user_active_flip"
    }
  ],
  "entryPoints": [
    {
      "forum-web": "ucp.php?mode=activate"
    }
  ]
}
---

# Activation

The working context for activation. Displayed facts follow their disclosure rules. Collected input does not disclose stored credential or proof verifiers.
