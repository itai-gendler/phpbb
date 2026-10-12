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
      "text": "The selected contribution is excluded by the visibility decision.",
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
      "text": "The missing/hidden result replaces its content; no hidden body is disclosed.",
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

# Read topic — hidden content

## Trigger

The selected contribution is excluded by the visibility decision.

## Outcome

The missing/hidden result replaces its content; no hidden body is disclosed.
