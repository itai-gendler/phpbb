---
{
  "kind": "primary",
  "routes": {
    "web": "Community browser"
  },
  "steps": [
    {
      "text": "The Moderator opens the open or closed report list.",
      "kind": "actor",
      "actor": "moderator",
      "entities": [],
      "contexts": {
        "web": {
          "place": "forum-web::community::post-reports"
        }
      }
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

# Browse post reports — community

## Trigger

The moderator opens the open or closed report list.

## Outcome

Filtered report identity, reason, reporter and time are displayed, or the list is empty.
