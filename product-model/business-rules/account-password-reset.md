---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "account",
      "effect": "changes",
      "facts": [
        "Credential",
        "Credential changed at"
      ],
      "contexts": [
        {
          "place": "forum-web::public::password-reset"
        },
        {
          "place": "forum-web::community::password-reset"
        }
      ]
    }
  ],
  "permits": [
    {
      "configuredBy": "board-settings",
      "when": [
        {
          "entity": "board-settings",
          "fact": "Password reset enabled",
          "is": true
        }
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/phpbb/ucp/controller/reset_password.php"
    }
  ]
}
---

# Account password reset requires the configured operation authority

Reset enabled, eligible target account and **that account’s** effective `u_chgpasswd`; link proof authenticates the claimant.
