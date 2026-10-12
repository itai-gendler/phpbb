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
      "text": "The selected report request reaches its refusal branch.",
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
      "text": "No report or snapshot is created.",
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

# Report post — denied

## Trigger

The selected report request reaches its refusal branch.

## Outcome

No report or snapshot is created.
