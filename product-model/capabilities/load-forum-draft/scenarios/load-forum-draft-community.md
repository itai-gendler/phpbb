---
{
  "kind": "primary",
  "routes": {
    "web": "Community browser"
  },
  "steps": [
    {
      "text": "The User selects a saved draft and its composing destination.",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "web": {
          "place": "forum-web::community::posting"
        }
      }
    },
    {
      "text": "The draft fills the posting editor; loading alone does not consume it or publish.",
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
        "web": {
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

# Load forum draft — community

## Trigger

The contributor selects a saved draft for a new-topic destination.

## Outcome

The draft fills the posting editor; loading alone does not consume it or publish.
