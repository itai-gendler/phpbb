---
{
  "kind": "validation",
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
      "text": "The replacement passwords mismatch or violate password validation.",
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
      "text": "The reset form retains the errors; the credential is not replaced.",
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

# Reset password — invalid password

## Trigger

The replacement passwords mismatch or violate password validation.

## Outcome

The reset form retains the errors; the credential is not replaced.
