---
{
  "kind": "primary",
  "routes": {
    "web": "Community browser"
  },
  "steps": [
    {
      "text": "The User submits a nonempty subject/content for a selected draft.",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "web": {
          "place": "forum-web::community::draft"
        }
      }
    },
    {
      "text": "The saved draft is changed and completion schedules Manage drafts.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "forum-draft",
          "effect": "changes",
          "facts": [
            "Subject",
            "Content"
          ]
        }
      ],
      "contexts": {
        "web": {
          "place": "forum-web::community::draft"
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

# Edit forum draft — community

## Trigger

The account holder submits a nonempty subject/content for a selected draft.

## Outcome

The saved draft is changed and completion schedules Manage drafts.
