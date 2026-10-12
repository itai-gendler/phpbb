---
{
  "kind": "primary",
  "routes": {
    "web": "Community browser"
  },
  "steps": [
    {
      "text": "The Administrator supplies the current administrative username/password and valid form.",
      "kind": "actor",
      "actor": "administrator",
      "entities": [],
      "contexts": {
        "web": {
          "place": "forum-web::community::login"
        }
      }
    },
    {
      "text": "Matching administrative credentials establish administrative confirmation and return to the requested Administration Control Panel destination.",
      "kind": "product",
      "actor": "administrator",
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

# Log in — community

## Trigger

The administrator supplies the current administrative username/password and valid form.

## Outcome

Matching administrative credentials establish administrative confirmation and return to the requested Administration Control Panel destination.
