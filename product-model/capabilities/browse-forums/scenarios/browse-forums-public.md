---
{
  "kind": "primary",
  "routes": {
    "web": "Public browser"
  },
  "steps": [
    {
      "text": "The Guest opens the board index.",
      "kind": "actor",
      "actor": "guest",
      "entities": [],
      "contexts": {
        "web": {
          "place": "forum-web::public::board-index"
        }
      }
    },
    {
      "text": "The hierarchy displays disclosed containers and contribution summaries; hidden branches are excluded.",
      "kind": "product",
      "actor": "guest",
      "entities": [
        {
          "entity": "forum",
          "effect": "reads",
          "facts": [
            "Name",
            "Description",
            "Parent",
            "Order",
            "Topic counts",
            "Last contribution"
          ]
        },
        {
          "entity": "category",
          "effect": "reads",
          "facts": [
            "Name",
            "Description",
            "Parent",
            "Order"
          ]
        },
        {
          "entity": "forum-link",
          "effect": "reads",
          "facts": [
            "Name",
            "Description",
            "Parent",
            "Order"
          ]
        }
      ],
      "contexts": {
        "web": {
          "place": "forum-web::public::board-index"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/index.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/viewforum.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/includes/functions_display.php#display_forums"
    }
  ]
}
---

# Browse forums — public

## Trigger

The visitor opens the board index.

## Outcome

The hierarchy displays disclosed containers and contribution summaries; hidden branches are excluded.
