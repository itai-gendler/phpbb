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
      "text": "Password reset is disabled.",
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
      "text": "The disabled-reset result replaces the reset process.",
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

# Reset password — reset disabled

## Trigger

Password reset is disabled.

## Outcome

The disabled-reset result replaces the reset process.
