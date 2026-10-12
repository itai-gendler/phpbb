---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "account",
      "effect": "changes",
      "facts": [
        "Reset proof",
        "Reset expiry"
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
      "configuredBy": "board-settings"
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

# Account reset proof maintenance requires the configured operation authority

Issuance follows eligible target-account reset authority; expiration cleanup follows the reset request before the later account eligibility check.

## Expiration cleanup

The request clears an expired token after selecting the actual target and before later eligibility evaluation. This cleanup is an alternative to eligible issuance, not a conjunction with password-reset eligibility.

## Expired replacement link

The reset-link handler first matches the supplied token. When that matching token has expired, it clears Reset proof and Reset expiry before returning the reset error and before later form/account-eligibility evaluation. A mismatched token does not trigger this cleanup.
