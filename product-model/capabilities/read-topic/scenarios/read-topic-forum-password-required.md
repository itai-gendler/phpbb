---
{
  "kind": "validation",
  "routes": {
    "public": "Public browser",
    "community": "Community browser"
  },
  "steps": [
    {
      "text": "The User opens an approved discussion.",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "public": {
          "place": "forum-web::public::topic"
        },
        "community": {
          "place": "forum-web::community::topic"
        }
      }
    },
    {
      "text": "The discussion belongs to a protected posting area without current access.",
      "kind": "condition",
      "actor": "user",
      "entities": [],
      "contexts": {
        "public": {
          "place": "forum-web::public::topic"
        },
        "community": {
          "place": "forum-web::community::topic"
        }
      }
    },
    {
      "text": "The posting area-password process is presented and the body remains undisclosed.",
      "kind": "product",
      "actor": "user",
      "entities": [],
      "contexts": {
        "public": {
          "place": "forum-web::public::topic"
        },
        "community": {
          "place": "forum-web::community::topic"
        }
      }
    }
  ],
  "references": [
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

# Read topic — forum password required

## Trigger

The discussion belongs to a protected forum without current access.

## Outcome

The forum-password process is presented and the body remains undisclosed.
