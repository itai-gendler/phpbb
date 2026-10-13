---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "account",
      "effect": "changes",
      "facts": [
        "Inactivity reason",
        "Activation proof",
        "Reset proof",
        "Reset expiry"
      ],
      "contexts": [
        {
          "place": "forum-web::public::activation"
        },
        {
          "place": "forum-web::community::activation"
        }
      ]
    }
  ],
  "permits": [
    {
      "actors": [
        "administrator"
      ]
    },
    {
      "actors": [
        "user"
      ],
      "when": [
        {
          "fact": "Inactivity reason",
          "is": "Forced reactivation"
        }
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
      "target": "phpBB/phpbb/notification/type/admin_activate_user.php"
    }
  ]
}
---

# Only an administrator activates a registered account

An administrator with effective `a_user` activates an account with its matching activation key. The account holder may only reactivate an account an administrator made Inactive for forced reactivation.

Under this policy, registration and an email change leave the account Inactive and alert administrators; the holder is told to wait for an administrator.
