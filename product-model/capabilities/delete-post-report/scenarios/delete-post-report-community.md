---
{
  "kind": "primary",
  "routes": {
    "web": "Community browser"
  },
  "steps": [
    {
      "text": "The Moderator confirms deletion of selected reports.",
      "kind": "actor",
      "actor": "moderator",
      "entities": [],
      "contexts": {
        "web": {
          "place": "forum-web::community::report-review"
        }
      }
    },
    {
      "text": "Selected reports are removed, reported flags recomputed and review-origin completion schedules the list.",
      "kind": "product",
      "actor": "moderator",
      "entities": [
        {
          "entity": "post-report",
          "effect": "removes",
          "from": "Open"
        },
        {
          "entity": "post",
          "effect": "changes",
          "facts": [
            "Reported"
          ]
        },
        {
          "entity": "topic",
          "effect": "changes",
          "facts": [
            "Reported"
          ]
        }
      ],
      "contexts": {
        "web": {
          "place": "forum-web::community::report-review"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/includes/mcp/mcp_reports.php#close_report"
    }
  ]
}
---

# Delete post report — community

## Trigger

The moderator confirms deletion of selected reports.

## Outcome

Selected reports are removed, reported flags recomputed and review-origin completion schedules the list.
