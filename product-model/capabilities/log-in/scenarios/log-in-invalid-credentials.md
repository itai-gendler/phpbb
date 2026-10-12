---
{
  "kind": "validation",
  "routes": {
    "public": "Public browser",
    "community": "Community browser"
  },
  "steps": [
    {
      "text": "The Administrator submits a username, password and the supplied form or challenge response.",
      "kind": "actor",
      "actor": "administrator",
      "entities": [],
      "contexts": {
        "public": {
          "place": "forum-web::public::login"
        },
        "community": {
          "place": "forum-web::community::login"
        }
      }
    },
    {
      "text": "The supplied username/password does not authenticate.",
      "kind": "condition",
      "actor": "administrator",
      "entities": [],
      "contexts": {
        "public": {
          "place": "forum-web::public::login"
        },
        "community": {
          "place": "forum-web::community::login"
        }
      }
    },
    {
      "text": "The credential failure is displayed; signed-in access is not established.",
      "kind": "product",
      "actor": "administrator",
      "entities": [],
      "contexts": {
        "public": {
          "place": "forum-web::public::login"
        },
        "community": {
          "place": "forum-web::community::login"
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

# Log in — invalid credentials

## Trigger

The supplied username/password does not authenticate.

## Outcome

The credential failure is displayed; signed-in access is not established.
