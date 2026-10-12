---
{
  "kind": "primary",
  "routes": {
    "web": "Public browser"
  },
  "steps": [
    {
      "text": "The Guest submits a reason and valid report input, challenge and form.",
      "kind": "actor",
      "actor": "guest",
      "entities": [],
      "contexts": {
        "web": {
          "place": "forum-web::public::post-report"
        }
      }
    },
    {
      "text": "The Product consults post Subject, Content, Formatting choices",
      "kind": "product",
      "actor": "guest",
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
          "place": "forum-web::public::post-report"
        }
      }
    },
    {
      "text": "An Open report captures content and formatting, sets reported flags and dispatches the report event; completion schedules the topic.",
      "kind": "product",
      "actor": "guest",
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
          "place": "forum-web::public::post-report"
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

# Report post — public

## Trigger

The reporter submits a reason and valid report input, challenge and form.

## Outcome

An Open report captures content and formatting, sets reported flags and dispatches the report event; completion schedules the topic.
