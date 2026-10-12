---
{
  "kind": "primary",
  "routes": {
    "web": "Public browser"
  },
  "steps": [
    {
      "text": "The User supplies the current username and password.",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "web": {
          "place": "forum-web::public::login"
        }
      }
    },
    {
      "text": "Matching credentials establish signed-in access and return to the requested destination.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "account",
          "effect": "reads",
          "facts": [
            "Username",
            "Credential",
            "Inactivity reason"
          ]
        }
      ],
      "contexts": {
        "web": {
          "place": "forum-web::public::login"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/ucp.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/includes/functions.php#login_box"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/phpbb/auth/provider/db.php#login"
    }
  ]
}
---

# Log in — public

## Trigger

The account holder supplies the current username and password.

## Outcome

Matching credentials establish signed-in access and return to the requested destination.
