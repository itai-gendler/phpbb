---
{
  "kind": "validation",
  "routes": {
    "public": "Public browser",
    "community": "Community browser"
  },
  "steps": [
    {
      "text": "The User submits a supplied reply in an existing discussion.",
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
      "text": "A quoted reply reaches the locked-destination refusal branch.",
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
      "text": "The lock result is displayed without storing the reply; the quoted submission is refused in this selected lock state.",
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

# Post reply — locked quote refused

## Trigger

A quoted reply reaches the locked-destination refusal branch.

## Outcome

The lock result is displayed without storing the reply; quote and literal reply use their distinct policy branches.
