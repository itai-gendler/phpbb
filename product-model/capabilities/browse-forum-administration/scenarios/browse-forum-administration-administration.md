---
{
  "kind": "primary",
  "routes": {
    "web": "Administration browser"
  },
  "steps": [
    {
      "text": "The Administrator opens Manage posting area.",
      "kind": "actor",
      "actor": "administrator",
      "entities": [],
      "contexts": {
        "web": {
          "place": "forum-web::administration::forum-management"
        }
      }
    },
    {
      "text": "The hierarchy displays container configuration and order.",
      "kind": "product",
      "actor": "administrator",
      "entities": [
        {
          "entity": "forum",
          "effect": "reads",
          "facts": [
            "Name",
            "Description",
            "Parent",
            "Order",
            "Topic counts",
            "Posting status"
          ]
        },
        {
          "entity": "category",
          "effect": "reads",
          "facts": [
            "Name",
            "Description",
            "Parent",
            "Order"
          ]
        },
        {
          "entity": "forum-link",
          "effect": "reads",
          "facts": [
            "Name",
            "Description",
            "Parent",
            "Order"
          ]
        }
      ],
      "contexts": {
        "web": {
          "place": "forum-web::administration::forum-management"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/includes/acp/acp_forums.php"
    }
  ]
}
---

# Browse forum administration — administration

## Trigger

The administrator opens Manage forums.

## Outcome

The hierarchy displays container configuration and order.
