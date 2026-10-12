---
{
  "entities": [
    {
      "entity": "account",
      "collects": [
        "Email",
        "Username",
        "Credential",
        "Reset proof"
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/phpbb/ucp/controller/reset_password.php#request"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/phpbb/ucp/controller/reset_password.php#reset"
    }
  ]
}
---

# Password reset

The working context for password reset. Displayed facts follow their disclosure rules. Collected input does not disclose stored credential or proof verifiers.
