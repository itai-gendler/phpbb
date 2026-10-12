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
      "text": "The applicable visitor challenge or form proof fails.",
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
      "text": "The report input is retained with errors; no report is created.",
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

# Report post — invalid challenge or form

## Trigger

The applicable guest challenge or form proof fails.

## Outcome

The report input is retained with errors; no report is created.
