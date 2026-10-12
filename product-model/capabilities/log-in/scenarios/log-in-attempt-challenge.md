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
      "text": "The configured failed-attempt threshold requires a challenge and its response fails.",
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
      "text": "The challenge/attempt failure is displayed and authentication remains incomplete.",
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

# Log in — attempt challenge

## Trigger

The configured failed-attempt threshold requires a challenge and its response fails.

## Outcome

The challenge/attempt failure is displayed and authentication remains incomplete.
