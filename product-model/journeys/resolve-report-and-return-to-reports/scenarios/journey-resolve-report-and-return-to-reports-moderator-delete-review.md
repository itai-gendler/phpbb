---
{
  "kind": "primary",
  "result": "achieved",
  "routes": {
    "web": "Browser carried completion"
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
      },
      "capability": "delete-post-report"
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
      },
      "capability": "delete-post-report"
    },
    {
      "text": "The Product carries Moderator through the completion destination into browse contribution reports",
      "kind": "product",
      "actor": "moderator",
      "capability": "delete-post-report",
      "entities": [],
      "contexts": {
        "web": {
          "place": "forum-web::community::report-review"
        }
      }
    },
    {
      "text": "The Moderator opens the open or closed report list.",
      "kind": "actor",
      "actor": "moderator",
      "entities": [],
      "contexts": {
        "web": {
          "place": "forum-web::community::post-reports"
        }
      },
      "capability": "browse-post-reports"
    },
    {
      "text": "Filtered report identity, reason, reporter and time are displayed, or the list is empty.",
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
            "Reported at"
          ]
        },
        {
          "entity": "post",
          "effect": "reads",
          "facts": [
            "Subject",
            "Author"
          ]
        }
      ],
      "contexts": {
        "web": {
          "place": "forum-web::community::post-reports"
        }
      },
      "capability": "browse-post-reports"
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

# Resolve report and return to reports — moderator delete review

## Trigger

Complete a report decision from review and reach the report list.

## Outcome

The reviewing moderator follows the close/delete completion destination to the reports list.
