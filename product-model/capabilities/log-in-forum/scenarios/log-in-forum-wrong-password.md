---
{
  "kind": "validation",
  "routes": {
    "public": "Public browser",
    "community": "Community browser"
  },
  "steps": [
    {
      "text": "The User supplies the entered protected-posting area password.",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "public": {
          "place": "forum-web::public::forum-login"
        },
        "community": {
          "place": "forum-web::community::forum-login"
        }
      }
    },
    {
      "text": "The supplied protected-posting area password does not match.",
      "kind": "condition",
      "actor": "user",
      "entities": [],
      "contexts": {
        "public": {
          "place": "forum-web::public::forum-login"
        },
        "community": {
          "place": "forum-web::community::forum-login"
        }
      }
    },
    {
      "text": "The password error is displayed and posting area access is not recorded.",
      "kind": "product",
      "actor": "user",
      "entities": [],
      "contexts": {
        "public": {
          "place": "forum-web::public::forum-login"
        },
        "community": {
          "place": "forum-web::community::forum-login"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/includes/functions.php#login_forum_box"
    }
  ]
}
---

# Log in forum — wrong password

## Trigger

The supplied protected-forum password does not match.

## Outcome

The password error is displayed and forum access is not recorded.
