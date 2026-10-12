---
{
  "kind": "validation",
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
      "text": "The reason is missing or Other lacks explanation.",
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
      "text": "The report form shows the reason error without creating a report.",
      "kind": "product",
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

# Report post — invalid reason

## Trigger

The reason is missing or Other lacks explanation.

## Outcome

The report form shows the reason error without creating a report.
