---
{
  "kind": "primary",
  "routes": {
    "web": "Community browser"
  },
  "steps": [
    {
      "text": "The Moderator confirms closure of selected Open reports.",
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
      "text": "The reports become Closed with snapshots retained, flags recomputed and applicable reporter dispatch; review-origin completion schedules the list.",
      "kind": "product",
      "actor": "moderator",
      "entities": [
        {
          "entity": "post-report",
          "effect": "changes",
          "facts": [],
          "from": "Open",
          "to": "Closed"
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

# Close post report — community

## Trigger

The moderator confirms closure of selected Open reports.

## Outcome

The reports become Closed with snapshots retained, flags recomputed and applicable reporter dispatch; review-origin completion schedules the list.
