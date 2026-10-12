---
{
  "kind": "validation",
  "routes": {
    "public": "Public browser",
    "community": "Community browser"
  },
  "steps": [
    {
      "text": "The User submits a supplied subject and content in a posting area.",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "public": {
          "place": "forum-web::public::posting"
        },
        "community": {
          "place": "forum-web::community::posting"
        }
      }
    },
    {
      "text": "The request hits its applicable registered identity-time or anonymous-IP flood limit.",
      "kind": "condition",
      "actor": "user",
      "entities": [],
      "contexts": {
        "public": {
          "place": "forum-web::public::posting"
        },
        "community": {
          "place": "forum-web::community::posting"
        }
      }
    },
    {
      "text": "The flood error is displayed without storing the proposed contribution.",
      "kind": "product",
      "actor": "user",
      "entities": [],
      "contexts": {
        "public": {
          "place": "forum-web::public::posting"
        },
        "community": {
          "place": "forum-web::community::posting"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/posting.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/includes/functions_posting.php#submit_post"
    }
  ]
}
---

# Post new topic — flood refusal

## Trigger

The request hits its applicable account-time or anonymous-IP flood limit.

## Outcome

The flood error is displayed without storing the proposed contribution.
