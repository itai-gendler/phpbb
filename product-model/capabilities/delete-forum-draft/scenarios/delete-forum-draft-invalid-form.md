---
{
  "kind": "validation",
  "routes": {
    "community": "Community browser"
  },
  "steps": [
    {
      "text": "The User submits selected draft removal with a supplied form.",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "community": {
          "place": "forum-web::community::drafts"
        }
      }
    },
    {
      "text": "The removal form proof fails.",
      "kind": "condition",
      "actor": "user",
      "entities": [],
      "contexts": {
        "community": {
          "place": "forum-web::community::drafts"
        }
      }
    },
    {
      "text": "FORM_INVALID is displayed without removing the selected saved drafts.",
      "kind": "product",
      "actor": "user",
      "entities": [],
      "contexts": {
        "community": {
          "place": "forum-web::community::drafts"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/includes/ucp/ucp_main.php"
    }
  ]
}
---

# Delete forum draft — invalid form

## Trigger

The removal form proof fails.

## Outcome

FORM_INVALID is displayed without removing the selected saved drafts.
