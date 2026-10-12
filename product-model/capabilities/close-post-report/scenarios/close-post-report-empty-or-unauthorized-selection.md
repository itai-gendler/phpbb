---
{
  "kind": "validation",
  "routes": {
    "community": "Community browser"
  },
  "steps": [
    {
      "text": "The Moderator confirms closure of selected Open reports.",
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
      "text": "No selected entries remain after validation/filtering.",
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
      "text": "The empty-selection result is displayed without closing a report.",
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

# Close post report — empty or unauthorized selection

## Trigger

No selected entries remain after validation/filtering.

## Outcome

The empty-selection result is displayed without closing a report.
