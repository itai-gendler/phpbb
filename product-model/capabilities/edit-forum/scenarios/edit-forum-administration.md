---
{
  "kind": "primary",
  "routes": {
    "web": "Administration browser"
  },
  "steps": [
    {
      "text": "The Administrator submits accepted configuration for a selected posting area.",
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
      "text": "Its configuration is saved and applicable hierarchy/content synchronization runs.",
      "kind": "product",
      "actor": "administrator",
      "entities": [
        {
          "entity": "forum",
          "effect": "changes",
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

# Edit forum — administration

## Trigger

The administrator submits accepted configuration for a selected forum.

## Outcome

Its configuration is saved and applicable hierarchy/content synchronization runs.
