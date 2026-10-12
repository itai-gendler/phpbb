---
{
  "kind": "validation",
  "routes": {
    "community": "Community browser"
  },
  "steps": [
    {
      "text": "The Administrator supplies the current administrative username/password and supplied form.",
      "kind": "actor",
      "actor": "administrator",
      "entities": [],
      "contexts": {
        "community": {
          "place": "forum-web::community::login"
        }
      }
    },
    {
      "text": "The signed-in administrative-authentication request fails its identity/entry checks.",
      "kind": "condition",
      "actor": "administrator",
      "entities": [],
      "contexts": {
        "community": {
          "place": "forum-web::community::login"
        }
      }
    },
    {
      "text": "Administrative confirmation is not established and the administrative login failure is displayed.",
      "kind": "product",
      "actor": "administrator",
      "entities": [],
      "contexts": {
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

# Log in — administration refused

## Trigger

The signed-in administrative-authentication request fails its identity/entry checks.

## Outcome

Administrative confirmation is not established and the administrative login failure is displayed.
