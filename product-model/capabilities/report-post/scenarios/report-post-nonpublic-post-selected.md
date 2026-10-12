---
{
  "kind": "edge",
  "routes": {
    "public": "Public browser",
    "community": "Community browser"
  },
  "steps": [
    {
      "text": "The User submits a reason and supplied report input, challenge and form.",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "public": {
          "place": "forum-web::public::post-report"
        },
        "community": {
          "place": "forum-web::community::post-report"
        }
      }
    },
    {
      "text": "An existing nonpublic contribution is selected through the report path.",
      "kind": "condition",
      "actor": "user",
      "entities": [],
      "contexts": {
        "public": {
          "place": "forum-web::public::post-report"
        },
        "community": {
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
        "public": {
          "place": "forum-web::public::post-report"
        },
        "community": {
          "place": "forum-web::community::post-report"
        }
      }
    },
    {
      "text": "An Open post report captures the selected content and formatting; the post and topic reported flags are set and the report result is displayed.",
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
        "public": {
          "place": "forum-web::public::post-report"
        },
        "community": {
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

# Report post — nonpublic post selected

## Trigger

An existing nonpublic contribution is selected through the report path.

## Outcome

An Open report captures the selected nonpublic content and formatting, sets reported flags and displays the report result.
