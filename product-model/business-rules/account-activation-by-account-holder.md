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
        "user",
        "administrator"
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
      "target": "phpBB/includes/ucp/ucp_resend.php"
    }
  ]
}
---

# The account holder activates their own account

Whoever presents an account's matching activation key activates it, normally the account holder following the emailed link.

Under this policy, registration and an email change leave the account Inactive and email the activation link to the holder, who may ask for it again.
