---
{
  "kind": "validation",
  "routes": {
    "community": "Community browser"
  },
  "steps": [
    {
      "text": "The User submits default posting choices with a supplied form.",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "community": {
          "place": "forum-web::community::account"
        }
      }
    },
    {
      "text": "The posting-default form proof fails.",
      "kind": "condition",
      "actor": "user",
      "entities": [],
      "contexts": {
        "community": {
          "place": "forum-web::community::account"
        }
      }
    },
    {
      "text": "FORM_INVALID is displayed and proposed defaults are not saved.",
      "kind": "product",
      "actor": "user",
      "entities": [],
      "contexts": {
        "community": {
          "place": "forum-web::community::account"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/includes/ucp/ucp_prefs.php"
    }
  ]
}
---

# Edit posting defaults — invalid form

## Trigger

The posting-default form proof fails.

## Outcome

FORM_INVALID is displayed and proposed defaults are not saved.
