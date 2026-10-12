---
{
  "kind": "primary",
  "routes": {
    "community": "Community browser"
  },
  "steps": [
    {
      "text": "The Moderator opens the open or closed report list.",
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
      "text": "The moderator selects an existing report for review.",
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
      "text": "The captured snapshot/reason/text/reporter/time and current governed post facts are displayed independently.",
      "kind": "product",
      "actor": "moderator",
      "entities": [
        {
          "entity": "post-report",
          "effect": "reads",
          "facts": [
            "Reporter",
            "Post",
            "Reason",
            "Text",
            "Notify reporter",
            "Reported at",
            "Content snapshot",
            "Snapshot formatting"
          ]
        },
        {
          "entity": "post",
          "effect": "reads",
          "facts": [
            "Subject",
            "Content",
            "Author",
            "Posted at",
            "Visibility",
            "Formatting choices"
          ]
        }
      ],
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

# Browse post reports — report details

## Trigger

The moderator selects an existing report for review.

## Outcome

The captured snapshot/reason/text/reporter/time and current governed post facts are displayed independently.
