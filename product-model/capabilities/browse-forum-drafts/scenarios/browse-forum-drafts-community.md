---
{
  "kind": "primary",
  "routes": {
    "web": "Community browser"
  },
  "steps": [
    {
      "text": "The User opens Manage drafts.",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "web": {
          "place": "forum-web::community::drafts"
        }
      }
    },
    {
      "text": "The list displays this registered identity's saved posting area drafts and available composing destinations.",
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
        "web": {
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

# Browse forum drafts — community

## Trigger

The account holder opens Manage drafts.

## Outcome

The list displays this account's saved forum drafts and available composing destinations.
