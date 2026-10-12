---
{
  "kind": "primary",
  "routes": {
    "web": "Community browser"
  },
  "steps": [
    {
      "text": "The User supplies the matching protected-posting area password.",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "web": {
          "place": "forum-web::community::forum-login"
        }
      }
    },
    {
      "text": "Access is recorded for the current authentication context and the intended destination resumes without a user-managed session object.",
      "kind": "product",
      "actor": "user",
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

# Log in forum — community

## Trigger

The visitor supplies the matching protected-forum password.

## Outcome

Access is recorded for the current authentication context and the intended destination resumes without a user-managed session object.
