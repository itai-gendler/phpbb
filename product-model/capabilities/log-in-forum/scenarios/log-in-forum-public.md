---
{
  "kind": "primary",
  "routes": {
    "web": "Public browser"
  },
  "steps": [
    {
      "text": "The Guest supplies the matching protected-posting area password.",
      "kind": "actor",
      "actor": "guest",
      "entities": [],
      "contexts": {
        "web": {
          "place": "forum-web::public::forum-login"
        }
      }
    },
    {
      "text": "Access is recorded for the current authentication context and the intended destination resumes without a member-managed session object.",
      "kind": "product",
      "actor": "guest",
      "entities": [
        {
          "entity": "forum",
          "effect": "reads",
          "facts": [
            "Password protection"
          ]
        }
      ],
      "contexts": {
        "web": {
          "place": "forum-web::public::forum-login"
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

# Log in forum — public

## Trigger

The visitor supplies the matching protected-forum password.

## Outcome

Access is recorded for the current authentication context and the intended destination resumes without a user-managed session object.
