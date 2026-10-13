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
      ],
      "when": [
        {
          "fact": "Inactivity reason",
          "is-not": "Manual"
        }
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/includes/ucp/ucp_activate.php"
    }
  ]
}
---

# A manually deactivated account is not activated through its link

Activation through the link needs the account's matching activation key and never applies to an account made Inactive manually. Supplied key matching is authentication. Who else may activate is set by the board's Registration mode.
