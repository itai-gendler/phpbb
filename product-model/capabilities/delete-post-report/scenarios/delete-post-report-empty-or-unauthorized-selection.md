---
{
  "kind": "validation",
  "routes": {
    "community": "Community browser"
  },
  "steps": [
    {
      "text": "The Moderator confirms deletion of selected reports.",
      "kind": "actor",
      "actor": "moderator",
      "entities": [],
      "contexts": {
        "community": {
          "place": "forum-web::community::report-review"
        }
      }
    },
    {
      "text": "No selected report entries remain after validation/filtering.",
      "kind": "condition",
      "actor": "moderator",
      "entities": [],
      "contexts": {
        "community": {
          "place": "forum-web::community::report-review"
        }
      }
    },
    {
      "text": "The empty-selection result is displayed without deleting a report.",
      "kind": "product",
      "actor": "moderator",
      "entities": [],
      "contexts": {
        "community": {
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

# Delete post report — empty or unauthorized selection

## Trigger

No selected report entries remain after validation/filtering.

## Outcome

The empty-selection result is displayed without deleting a report.
