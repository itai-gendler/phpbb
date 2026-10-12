---
{
  "kind": "primary",
  "result": "achieved",
  "routes": {
    "web": "Browser carried completion"
  },
  "steps": [
    {
      "text": "The Guest submits a reason and supplied report input, challenge and form.",
      "kind": "actor",
      "actor": "guest",
      "entities": [],
      "contexts": {
        "web": {
          "place": "forum-web::public::post-report"
        }
      },
      "capability": "report-post"
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
      },
      "capability": "report-post"
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
      },
      "capability": "report-post"
    },
    {
      "text": "The Product carries Guest through the completion destination into read discussion",
      "kind": "product",
      "actor": "guest",
      "capability": "report-post",
      "entities": [],
      "contexts": {
        "web": {
          "place": "forum-web::public::post-report"
        }
      }
    },
    {
      "text": "The Guest opens an approved discussion.",
      "kind": "actor",
      "actor": "guest",
      "entities": [],
      "contexts": {
        "web": {
          "place": "forum-web::public::topic"
        }
      },
      "capability": "read-topic"
    },
    {
      "text": "The Product consults topic Subject, Author, Approved count, Last contribution",
      "kind": "product",
      "actor": "guest",
      "entities": [
        {
          "entity": "topic",
          "effect": "reads",
          "facts": [
            "Subject",
            "Author",
            "Approved count",
            "Last contribution"
          ]
        }
      ],
      "contexts": {
        "web": {
          "place": "forum-web::public::topic"
        }
      },
      "capability": "read-topic"
    },
    {
      "text": "The discussion presents its disclosed contributions and author information; reading increments the applicable view summary.",
      "kind": "product",
      "actor": "guest",
      "entities": [
        {
          "entity": "post",
          "effect": "reads",
          "facts": [
            "Subject",
            "Content",
            "Author",
            "Guest name",
            "Posted at",
            "Edit information",
            "Visibility",
            "Formatting choices"
          ]
        },
        {
          "entity": "topic",
          "effect": "changes",
          "facts": [
            "Views"
          ]
        }
      ],
      "contexts": {
        "web": {
          "place": "forum-web::public::topic"
        }
      },
      "capability": "read-topic"
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
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/viewtopic.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/phpbb/content_visibility.php#is_visible"
    }
  ]
}
---

# Report and return to topic — guest report

## Trigger

Submit a post report and reach the readable discussion destination.

## Outcome

The reporter completes reporting then reads the topic carried by the completion destination.
