---
{
  "kind": "validation",
  "routes": {
    "public": "Public browser",
    "community": "Community browser"
  },
  "steps": [
    {
      "text": "The User follows a reset link whose supplied token matches but has expired.",
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
      "text": "The matched reset proof’s expiry precedes the current request time.",
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
      "text": "The account Reset proof and Reset expiry are cleared, the reset error is displayed, and Credential remains unchanged.",
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

# Reset password — invalid token

## Trigger

The supplied reset token matches the selected account but its expiry has passed.


## Outcome

The expired reset data is cleared before the reset error; the credential is not replaced.


## Edge cases

- Replacement also fails for an ineligible target identity or its disabled password-change route; proof authentication is separate from the target policy.
- A mismatched or missing token returns its reset error without clearing another valid proof.
- Failed form proof with a still-valid matching token returns FORM_INVALID without replacing Credential or clearing the token.
