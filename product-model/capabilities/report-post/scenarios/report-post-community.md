---
{
  "kind": "primary",
  "routes": {
    "web": "Community browser"
  },
  "steps": [
    {
      "text": "The User submits a reason and valid report input, challenge and form.",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "web": {
          "place": "forum-web::community::post-report"
        }
      }
    },
    {
      "text": "The Product consults post Subject, Content, Formatting choices",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "post",
          "effect": "reads",
          "facts": [
            "Subject",
            "Content",
            "Formatting choices"
          ]
        }
      ],
      "contexts": {
        "web": {
          "place": "forum-web::community::post-report"
        }
      }
    },
    {
      "text": "An Open report captures content and formatting, sets reported flags and dispatches the report event; completion schedules the topic.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "post-report",
          "effect": "creates",
          "facts": [
            "Reporter",
            "Post",
            "Reason",
            "Text",
            "Notify reporter",
            "Reported at",
            "Content snapshot",
            "Snapshot formatting"
          ],
          "to": "Open"
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
          "place": "forum-web::community::post-report"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/phpbb/report/controller/report.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/phpbb/report/report_handler_post.php"
    }
  ]
}
---

# Report post — community

## Trigger

The reporter submits a reason and valid report input, challenge and form.

## Outcome

An Open report captures content and formatting, sets reported flags and dispatches the report event; completion schedules the topic.
