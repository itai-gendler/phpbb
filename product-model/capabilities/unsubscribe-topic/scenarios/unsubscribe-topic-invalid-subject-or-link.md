---
{
  "kind": "validation",
  "routes": {
    "community": "Community browser"
  },
  "steps": [
    {
      "text": "The User follows a supplied stop-watching-discussion link.",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "community": {
          "place": "forum-web::community::topic"
        }
      }
    },
    {
      "text": "The request carries mismatched registered identity/subject/op information or invalid shortcut proof.",
      "kind": "condition",
      "actor": "user",
      "entities": [],
      "contexts": {
        "community": {
          "place": "forum-web::community::topic"
        }
      }
    },
    {
      "text": "The stop-watching failure is displayed without removing an entry.",
      "kind": "product",
      "actor": "user",
      "entities": [],
      "contexts": {
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
      "target": "phpBB/includes/functions_display.php#watch_topic_forum"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/includes/ucp/ucp_main.php"
    }
  ]
}
---

# Unsubscribe topic — invalid subject or link

## Trigger

The request carries mismatched account/subject/op information or invalid shortcut proof.

## Outcome

The stop-watching failure is displayed without removing an entry.
