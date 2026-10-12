---
{
  "kind": "primary",
  "routes": {
    "public": "Public browser",
    "community": "Community browser"
  },
  "steps": [
    {
      "text": "The User requests a reset then follows the issued link and submits supplied new passwords.",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "public": {
          "place": "forum-web::public::password-reset"
        },
        "community": {
          "place": "forum-web::community::password-reset"
        }
      }
    },
    {
      "text": "The request selects an inactive existing identity with an expired reset proof.",
      "kind": "condition",
      "actor": "user",
      "entities": [],
      "contexts": {
        "public": {
          "place": "forum-web::public::password-reset"
        },
        "community": {
          "place": "forum-web::community::password-reset"
        }
      }
    },
    {
      "text": "The account’s expired Reset proof and Reset expiry are cleared and the generic acknowledgement is returned without issuing a new proof.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "account",
          "effect": "changes",
          "facts": [
            "Reset proof",
            "Reset expiry"
          ]
        }
      ],
      "contexts": {
        "public": {
          "place": "forum-web::public::password-reset"
        },
        "community": {
          "place": "forum-web::community::password-reset"
        }
      }
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

# Reset password — generic ineligible acknowledgement

## Trigger

The request selects an inactive existing account with an expired reset proof.


## Outcome

The expired reset data is cleared before eligibility evaluation; the generic acknowledgement follows without a new proof.

## Edge cases

- Unknown identities return the same generic acknowledgement without changing an account.
- Inactive or ignored targets with no expired proof retain their reset data and receive no new proof.
