---
{
  "kind": "primary",
  "routes": {
    "community": "Community browser"
  },
  "steps": [
    {
      "text": "The User opens Manage drafts.",
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
      "text": "The draft store contains another registered identity's drafts.",
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
      "text": "Only the current registered identity's posting area drafts are displayed.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "forum-draft",
          "effect": "reads",
          "facts": [
            "Subject",
            "Author",
            "Saved at",
            "Forum",
            "Topic"
          ]
        }
      ],
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

# Browse forum drafts — unowned drafts filtered

## Trigger

The draft store contains another account's drafts.

## Outcome

Only the current account's forum drafts are displayed.
