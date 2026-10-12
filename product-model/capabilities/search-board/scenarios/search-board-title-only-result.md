---
{
  "kind": "primary",
  "routes": {
    "public": "Public browser",
    "community": "Community browser"
  },
  "steps": [
    {
      "text": "The User submits a supplied query and search options.",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "public": {
          "place": "forum-web::public::search"
        },
        "community": {
          "place": "forum-web::community::search"
        }
      }
    },
    {
      "text": "The selected search branch includes a posting area with title-list access only.",
      "kind": "condition",
      "actor": "user",
      "entities": [],
      "contexts": {
        "public": {
          "place": "forum-web::public::search"
        },
        "community": {
          "place": "forum-web::community::search"
        }
      }
    },
    {
      "text": "Only admitted topic-title results from that posting area are shown, not its contribution content.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "topic",
          "effect": "reads",
          "facts": [
            "Subject",
            "Author",
            "Created at",
            "Last contribution"
          ]
        }
      ],
      "contexts": {
        "public": {
          "place": "forum-web::public::search"
        },
        "community": {
          "place": "forum-web::community::search"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/search.php"
    }
  ]
}
---

# Search board — title only result

## Trigger

The selected search branch includes a forum with title-list access only.

## Outcome

Only admitted topic-title results from that forum are shown, not its post content.
