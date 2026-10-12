---
{
  "kind": "primary",
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
      "text": "The selection includes reports already Closed.",
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
      "text": "The closed result remains Closed; flag recomputation follows the handler without content deletion.",
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

# Close post report — already closed

## Trigger

The selection includes reports already Closed.

## Outcome

The closed result remains Closed; flag recomputation follows the handler without content deletion.
