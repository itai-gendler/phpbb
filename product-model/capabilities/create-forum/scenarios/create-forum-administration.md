---
{
  "kind": "primary",
  "routes": {
    "web": "Administration browser"
  },
  "steps": [
    {
      "text": "The Administrator submits valid posting area configuration without copied permissions.",
      "kind": "actor",
      "actor": "administrator",
      "entities": [],
      "contexts": {
        "web": {
          "place": "forum-web::administration::forum"
        }
      }
    },
    {
      "text": "A forum is created; the creation branch can schedule forum-permission assignment, otherwise completion shows the creation result.",
      "kind": "product",
      "actor": "administrator",
      "entities": [
        {
          "entity": "forum",
          "effect": "creates",
          "facts": [
            "Name",
            "Description",
            "Parent",
            "Order",
            "Rules",
            "Password protection",
            "Posting status",
            "Posting options",
            "Post review",
            "Post-count policy",
            "Topic counts",
            "Last contribution",
            "Pruning settings"
          ]
        }
      ],
      "contexts": {
        "web": {
          "place": "forum-web::administration::forum"
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

# Create forum — administration

## Trigger

The administrator submits valid posting-forum configuration without copied permissions.

## Outcome

A forum is created; the creation branch can schedule forum-permission assignment, otherwise completion shows the creation result.
