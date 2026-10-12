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
      "text": "The submitted email matches multiple registered identity and username was omitted.",
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
      "text": "The request asks for the registered identity username; it does not choose an arbitrary registered identity or issue a proof.",
      "kind": "product",
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

# Reset password — username required

## Trigger

The submitted email matches multiple accounts and username was omitted.

## Outcome

The request asks for the account username; it does not choose an arbitrary account or issue a proof.
