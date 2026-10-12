---
{
  "kind": "validation",
  "routes": {
    "public": "Public browser"
  },
  "steps": [
    {
      "text": "The User submits a username, password and the supplied form or challenge response.",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "public": {
          "place": "forum-web::public::login"
        }
      }
    },
    {
      "text": "The supplied credentials identify an inactive registered identity.",
      "kind": "condition",
      "actor": "user",
      "entities": [],
      "contexts": {
        "public": {
          "place": "forum-web::public::login"
        }
      }
    },
    {
      "text": "The inactive-registered identity result is displayed; signed-in access is not established.",
      "kind": "product",
      "actor": "user",
      "entities": [],
      "contexts": {
        "public": {
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

# Log in — inactive account

## Trigger

The supplied credentials identify an inactive account.

## Outcome

The inactive-account result is displayed; signed-in access is not established.
