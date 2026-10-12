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
      "configuredBy": "board-settings"
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

# Account activation requires the configured operation authority

Configured activation route and eligible inactivity reason; administrator activation requires effective `a_user`. Supplied key matching is authentication.
