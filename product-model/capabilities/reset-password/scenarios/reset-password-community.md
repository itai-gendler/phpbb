---
{
  "kind": "primary",
  "routes": {
    "web": "Community browser"
  },
  "steps": [
    {
      "text": "The User requests a password reset using the registered email and applicable username.",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "web": {
          "place": "forum-web::community::password-reset"
        }
      }
    },
    {
      "text": "The Product stores the reset proof and expiry and dispatches the reset link",
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
        "web": {
          "place": "forum-web::community::password-reset"
        }
      }
    },
    {
      "text": "The User follows the reset link and supplies matching replacement passwords",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "web": {
          "place": "forum-web::community::password-reset"
        }
      }
    },
    {
      "text": "The account Credential and its change time are replaced; reset proof/expiry and failed-attempt data are cleared, remembered keys reset and completion schedules the board.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "account",
          "effect": "changes",
          "facts": [
            "Credential",
            "Credential changed at",
            "Reset proof",
            "Reset expiry"
          ]
        }
      ],
      "contexts": {
        "web": {
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

# Reset password — community

## Trigger

The account holder requests a reset then follows the issued link and submits matching valid new passwords.

## Outcome

Issuance keeps a reset proof/expiry and dispatches the link; replacement changes the credential/time, clears reset data and attempts, resets remembered keys and schedules the board.
