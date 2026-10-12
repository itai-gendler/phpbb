---
{
  "kind": "primary",
  "routes": {
    "community": "Community browser"
  },
  "steps": [
    {
      "text": "The User selects a saved draft and its composing destination.",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "community": {
          "place": "forum-web::community::posting"
        }
      }
    },
    {
      "text": "The saved destination resolves to an existing readable discussion.",
      "kind": "condition",
      "actor": "user",
      "entities": [],
      "contexts": {
        "community": {
          "place": "forum-web::community::posting"
        }
      }
    },
    {
      "text": "The editor opens for reply with the selected draft's subject/content; a missing discussion can fall back to the posting area new-discussion destination.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "forum-draft",
          "effect": "reads",
          "facts": [
            "Subject",
            "Content",
            "Forum",
            "Topic"
          ]
        }
      ],
      "contexts": {
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

# Load forum draft — reply destination

## Trigger

The saved destination resolves to an existing readable topic.

## Outcome

The editor opens for reply with the selected draft's subject/content; a missing topic can fall back to the forum new-topic destination.
